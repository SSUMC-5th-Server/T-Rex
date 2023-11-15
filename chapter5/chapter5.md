가보자고chap4

저번에 설계한 ERD를 기반으로 SQL 문법을 작성하였다.

![a](picture/myERD.png)
저번에 작성한 것이다. 

각각에 미션에 대해 작성했다.
![a](picture/mission1.png)
p1.
// 진행중 
SELECT 
  mission.name
FROM
 mission
JOIN
 mymission
ON
 mymission.mission_id = mission.id
WHERE mymission.doing_done=false
limit 10 offset(n-1)*10;

// 진행완료
SELECT 
  mission.name
FROM
 mission
JOIN
 mymission
ON
 mymission.mission_id = mission.id
WHERE mymission.doing_done=true
limit 10 offset(n-1)*10;

![a](picture/mission2.png)
p2.
//가게에 대한 리뷰
SELECT
 review.title, review.body
FROM
 shop
JOIN
 review
ON 
 shop.id = review.shop_id




![a](picture/mission3.png)
p3.
//내가 모은 미션 수
SELECT
 member.mission_count
FROM 
 member
WHERE
 member.id = 3

//내가 아직 하지 않은 미션
SELECT *
FROM mission
LEFT JOIN mymission
ON mymission.mission_id = mission.id and mymission.doing_done = true
WHERE mymission.key is null;

![a](picture/mission4.png)
p4.
SELECT
  memver.*, review.title, review.body
FROM
  member 
LEFT JOIN
  review
ON
  member.id = review.member_id
WHERE
  member.id = 3;


