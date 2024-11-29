# MediHub-BE


## 👩🏻‍💻 제1조1항 🧑🏻‍💻

| [![](https://avatars.githubusercontent.com/u/173455095?v=4)](https://github.com/SANGHYUN0519) | [![](https://avatars.githubusercontent.com/u/158060587?v=4)](https://github.com/ygc1994) | [![](https://avatars.githubusercontent.com/u/173458380?v=4)](https://github.com/JIYOUNG-22) | [![](https://avatars.githubusercontent.com/u/103546300?v=4)](https://github.com/Pangtaek) | [![](https://avatars.githubusercontent.com/u/94957124?v=4)](https://github.com/person76) | [<img src="https://github.com/user-attachments/assets/4d62fcb6-1511-4e22-86da-1704a26180d9" width="450" />](https://github.com/PBEM22) |
|--------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------|------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------|
| <p align="center">박상현</p> | <p align="center">연건창</p> | <p align="center">윤지영</p> | <p align="center">임광택</p> | <p align="center">임서연</p> | <p align="center">임채륜</p> |

<br>

## 🛠️ 기술 스택

<img src="https://img.shields.io/badge/java-007396?style=for-the-badge&logo=java&logoColor=white"> <img src="https://img.shields.io/badge/springboot-6DB33F?style=for-the-badge&logo=springboot&logoColor=white">
<img src="https://img.shields.io/badge/spring data JPA-6DB33F?style=for-the-badge&logo=hibernate&logoColor=white">
<img src="https://img.shields.io/badge/spring%20security-6DB33F?style=for-the-badge&logo=springsecurity&logoColor=white">
<br>
<img src="https://img.shields.io/badge/html5-E34F26?style=for-the-badge&logo=html5&logoColor=white"> 
<img src="https://img.shields.io/badge/css-1572B6?style=for-the-badge&logo=css3&logoColor=white"> 
<img src="https://img.shields.io/badge/javascript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black">
<img src="https://img.shields.io/badge/vue.js-4FC08D?style=for-the-badge&logo=vue.js&logoColor=white">
<br>
<img src="https://img.shields.io/badge/docker-%230db7ed.svg?style=for-the-badge&logo=docker&logoColor=white">
<img src="https://img.shields.io/badge/kubernetes-%23326ce5.svg?style=for-the-badge&logo=kubernetes&logoColor=white">
<img src="https://img.shields.io/badge/jenkins-%232C5263.svg?style=for-the-badge&logo=jenkins&logoColor=white">
<br>
<img src="https://img.shields.io/badge/mariadb-4479A1?style=for-the-badge&logo=mariadb&logoColor=white">
<img src="https://img.shields.io/badge/Amazon%20S3-FF9900?style=for-the-badge&logo=amazons3&logoColor=white">
<br>
<img src="https://img.shields.io/badge/github-181717?style=for-the-badge&logo=github&logoColor=white">
<img src="https://img.shields.io/badge/figma-F24E1E?style=for-the-badge&logo=figma&logoColor=white">

<br>

## 📜 목차
1. [프로젝트 기획서](#1-프로젝트-기획서)
2. [WBS](#2-wbs)
3. [DDD 설계](#3-ddd-설계)
4. [요구사항 명세서](#4-요구사항-명세서)
5. [Database 설계](#5-database-설계)
6. [화면 설계서](#6-화면-설계서)
7. [시스템 아키텍처](#7-시스템-아키텍처)

<hr>

## 프로젝트 개요
> <b>[MediHub]</b>
> <br>
>

<br>

## 1. 프로젝트 기획서
[프로젝트 기획서](https://docs.google.com/document/d/1-ND5Wz1T14ndjffN6jAfWhBTUUeX5B-A93sHcd4FhfM/edit?tab=t.0)

## 2. WBS
[WBS](https://docs.google.com/spreadsheets/d/1sWHGbgL9R79AbUzCAmxKIulggjMqbi1lwv-RsJdtgVA/edit?gid=1194459417#gid=1194459417)

## 3. DDD 설계
[DDD](https://miro.com/app/board/uXjVLFIor4Y=/)

## 4. 요구사항 명세서
[요구사항명세서](https://docs.google.com/spreadsheets/d/1sWHGbgL9R79AbUzCAmxKIulggjMqbi1lwv-RsJdtgVA/edit?gid=205274512#gid=205274512)

## 5. Database 설계
[ERD](https://www.erdcloud.com/d/EmGTuF2SJmXwbLNiv)
<br>
<details>
<summary>MongoDB Schema</summary>
<div markdown="1">

### ChatUser Collection
```mongodb-json
{
  "UserSeq": "123",
  "Name": "홍길동",
  "Groups": ["group1", "group2"],  // 사용자가 참여한 그룹들
  "GroupCount": 2,                 // 참여 채팅방 개수
  "Status": "online",              // 사용자 상태 (online, offline, away 등)
  "ProfileImage": "https://example.com/profile.jpg",  // 프로필 사진 URL
  "LastActiveAt": "2024-11-29T15:34:21Z",               // 마지막 활동 시간
  "GlobalMute": false              // 모든 채팅방에서 알림 음소거 여부
}
```

### ChatGroup Collection
```mongodb-json
{
  "GroupSeq": "group1",
  "Name": "정형외과 공지방",
  "TotalMessages": 150,  // 총 메시지 수
  "LastMessageAt": "2024-11-29T15:34:21Z",  // 마지막 메시지 전송 시간
  "LastModified": "2024-11-29T15:00:00Z",   // 채팅방 마지막 수정 시간 (예: 이름 변경, 참여자 추가 등)
  "CreatedAt" : "2024-11-29T15:00:00Z",     // 채팅방 생성 시간
  "DeletedAt" : "",                         // 채팅방 삭제 시간
  "Users": [
    {
      "userSeq": "123",
      "RoomName" : "공지공지방",               // 개인별 채팅방 이름 설정
      "TotalUnread": 5,                     // 읽지 않은 메시지 수
      "JoinedAt": "2024-11-01T10:00:00Z"    // 채팅방에 참여한 시간
    },
    {
      "userId": "456",
      "RoomName" : "읽지마",
      "TotalUnread": 2,
      "JoinedAt": "2024-11-10T14:00:00Z"
    }
  ]
}
```

### ChatMessage Collection
```mongodb-json
{
	"MessageSeq": "msg1",
  "GroupSeq": "group1",
  "MessageContent": "회의자료를 첨부합니다.",
  "SendUser": {
    "userSeq": "123",
    "Name": "홍길동",
    "ProfileImage": "https://example.com/profile.jpg",  // 프로필 사진 URL
  },
  "CreatedAt": "2024-11-29T15:34:21Z",  // 메시지 전송 시간
  "Type": "file",                       // 메시지 타입 (text, image, file 등)
  "IsDeleted": false,                   // 메시지 삭제 여부
  "Attachments": [                      // 첨부파일 정보
    {
      "FileType": "image",  // 파일 타입 (image, document, video 등)
      "FileUrl": "https://example.com/path/to/image.jpg",  // 파일의 URL
      "FileName": "image.jpg",  // 파일 이름
      "FileSize": 123456  // 파일 크기 (바이트 단위)
    },
    {
      "FileType": "document",
      "FileUrl": "https://example.com/path/to/document.pdf",
      "FileName": "meeting_minutes.pdf",
      "FileSize": 234567
    }
  ]
}
```

### ChatFileStorage Collection
```mongodb-json
{
  "FileSeq": "12345",  // 자동 생성된 고유 ID (ObjectId)
  "UserSeq": "user123",  // 파일을 받은 사용자 ID
  "GroupSeq": "group1",  // 파일이 속한 채팅방 ID
  "MessageSeq": "msg123",  // 해당 파일이 포함된 메시지 ID
  "FileType": "image",  // 파일 유형 (image, document, video 등)
  "FileUrl": "https://example.com/path/to/image.jpg",  // 파일의 URL
  "FileName": "image.jpg",  // 파일 이름
  "FileSize": 1048576,  // 파일 크기 (바이트 단위)
  "UploadedAt": "2024-11-29T15:34:21Z",  // 파일이 첨부된 시간
  "ReceivedAt": "2024-11-29T15:35:21Z",  // 사용자가 파일을 받은 시간
  "ReadBy": ["123", "456"]  // 파일을 다운로드한/열어본 사용자 목록
}
```


</div>
</details>

## 6. 화면 설계서
[화면 설계서 (Figma)](https://www.figma.com/design/SiXw9eqSH2yS3GFtUxoINf/MediHub?node-id=0-1&node-type=canvas&t=yScI0V8n8O79M0vo-0)

## 7. 시스템 아키텍처
