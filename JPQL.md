 ```java
 // JPQL를 사용하여 공지사항(Notice) 검색
 public Header<List<Notice>> list(Integer type, String title,  String dateStart, String dateEnd, Integer startPage){
        String jpql = "select n from Notice n"; // Select할 쿼리문 조건
        boolean check = false;

        
        if(type != null || title != null  ||  dateStart != null || dateEnd != null){
            jpql += " where";
            if(type != null){ // 공지사항 type 
                jpql += " n_type = :type";
                check = true;
            }
            if (title != null){ // 공지사항 title
                if(check) jpql += " and";
                jpql += " title like :title";
                check = true;
            }
            if (dateStart != null){ // 검색할 날짜 범위(시작)
                if(check) jpql += " and";
                jpql += " TO_char(regdate, 'YYYY-MM-DD') >= :dateStart";
                check = true;
            }
            if(dateEnd != null){  // 검색할 날짜 범위(끝)
                if (check) jpql += " and";
                jpql += " TO_char(regdate, 'YYYY-MM-DD') <= :dateEnd";
            }
        }

        jpql += " order by idx desc"; // 내림차순으로 정렬
        
        // JPQL 실행 시 쿼리 객체 생성이 필요
        // TypedQuery : 반환할 타입을 명확하게 지정할 수 있는 경우
        // Query : 반환 타입을 명확하게 지정할 수 없는 경우 or 여러 엔티티, 컬럼을 선택할 경우
        TypedQuery<Notice> query = em.createQuery(jpql, Notice.class);  // 반환 타입 : Notice Entity

        // 일치하는 해당 쿼리 파라미터 바인딩
        if (type != null) query = query.setParameter("type", type); // type  조회
        if (title != null) query = query.setParameter("title", "%"+title+"%");  // title 조회
        if (dateStart != null) query = query.setParameter("dateStart", dateStart);  // 검색(시작) 날짜 조회
        if (dateEnd != null) query = query.setParameter("dateEnd", dateEnd);  // 검색(끝) 날짜 조회

        // 결과 조회
        List<Notice> result = query.getResultList();  

        int count = 10;

        int start = (count * startPage);
        int end = Math.min(result.size(), start + count);

        Pagination pagination = new Pagination().builder()
                .totalPages(result.size()/count)
                .totalElements(noticeRepository.count())
                .currentPage(startPage)
                .currentElements(result.size())
                .build();

        return Header.OK(result.subList(start, end), pagination);
    }
 
