각자의 페이지에서 가져와야 하는것이 무엇인지 먼저 정리하고 api 를 짜 보겠다

![a](picture/회원가입.png)
1. 회원가입
이름
성별
생년월일
주소
선호하는 음식

이후 key를 가져온다

Post /api/...
requestBody
{
    "name" = "이우혁",
    "gender"= "1",
    "birthDay" = "20010419",
    "favor" = ["한식", "도시락"],
    "region_address" = "인천",
    "spec_address"= "남동구 구월로 192"
}
resposeBody
{
    "memberId":1,
    "accessToken":....
}


![a](picture/홈화면.png)
2. 홈화면
지역명
내가 달성한 미션들 개수
내가 도전할 수 있는 미션들 쭉 보여주기 (
    미션하는 가게 이름, 
    미션하는 가게의 식당분류,
    미션 종료시간 - d-7,
    미션이 달성되는 조건
    포인트
)

Get /api/...
responseBody
{
    "region_address"="인천",
    "mission_count"="7",
    "mission" = [
		{
			"mission_id" : "1"
			"shop_name" : "반이학생마라탕"
			"deadline" : "20231212"
			"mission_how_success" : "10,000원 이상의 식사"
            "food_type"="중식당"
			"point" : "500"
		},
		{
			"mission_id" : "2"
			"shop_name" : "반이학생마라탕"
			"deadline" : "20231212"
			"mission_how_success" : "10,000원 이상의 식사"
            "food_type"="중식당"
			"point" : "500"
		}
	]

}




![a](picture/미션완료.png)
3. 미션 완료
하나의 미션 (
    가게 이름,
    미션 성공시 보상 - 5%적립,
    미션이 달성되는 조건
)

이후 사장님 구분 번호를 가져온다

![a](picture/미션목록조회(진행중,%20진행완료).png)
4. 미션 목록 조회
진행중인 미션들 목록
하나의 미션 (
    가게 이름,
    미션 성공시 보상 - 5%적립,
    미션이 달성되는 조건
)

진행완료 미션들 목록
하나의 미션 (
    가게 이름,
    미션 성공시 보상 - 5%적립,
    미션이 달성되는 조건
)

responseBody
{
    "mission" = [
		{
			"mission_id" : "1"
			"shop_name" : "반이학생마라탕"
			"deadline" : "20231212"
			"mission_how_success" : "10,000원 이상의 식사"
            "food_type"="중식당"
			"point" : "500"
		},
		{
			"mission_id" : "2"
			"shop_name" : "반이학생마라탕"
			"deadline" : "20231212"
			"mission_how_success" : "10,000원 이상의 식사"
            "food_type"="중식당"
			"point" : "500"
		}
	]
}



![a](picture/마이페이지%20리뷰작성.png)
5-1.마이페이지
내 포인트
포인트 내역 - 진행완료 미션들 목록
리뷰 클릭시 그 가게에 대한 모든 리뷰
내가 작성한 리뷰

responseBody
{
    "member_point" = "500"
    "mymission" = [
        {
			"mission_id" : "1"
			"shop_name" : "반이학생마라탕"
            "food_type"="중식당"
			"point" : "500"
		},
		{
			"mission_id" : "2"
			"shop_name" : "반이학생마라탕"
            "food_type"="중식당"
			"point" : "500"
		}
    ]
}

5-2.마이페이지 리뷰작성
리뷰 닉네임
리뷰 작성 날짜
별점
리뷰내용

requestBody
{
    "review_id" : "1"
	"user-id" : "이우혁"
	"reviewstar" : "5"
	"contents" : "리뷰내용"
	"review_date" : "2022.05.14"
	"shop_id" : "1"

}
