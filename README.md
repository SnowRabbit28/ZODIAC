<img width="1920" height="1080" alt="조디악" src="https://github.com/user-attachments/assets/aff01cbb-867e-43b1-9641-6b60456bac0a" />

# 프로젝트명:  ZODIAC
> 내일배움 캠프 Unity 6기 최종프로젝트

> 2024.11.25 ~ 2025.01.21


<div align=center>
 <img width="743" height="420" alt="브로셔" src="https://github.com/user-attachments/assets/114f0412-19c3-45e0-a42e-edc0182e1091" />
</div>
<br />


## ⭐ 게임 소개


- 별의 아이가 어둠에 맞서 황도 12궁의 별자리를 탐험하며 빛을 되찾는 이야기로
  <br />
  **어드벤처**, **퍼즐** 요소들을 결합하여 재미있게 풀어낸 작품입니다.



  <br />
## 📼 시연 영상
- [ youtube ](https://www.youtube.com/watch?v=vQS3qgq4FOA)
  <br />


  <br />
## 🕹️ 게임 링크
- [ itch.io ](https://zodiaccompany.itch.io/zodiac)
- [ steam ](https://store.steampowered.com/app/3508740/ZODIAC/#app_reviews_hash)
  <br />


  <br />
## ⚙️ 기술스택
- Language: C#
- IDE: Visual Studio, Rider
- GameEngine: Unity - 2022.3.17f1
  <br />



  <br />
  <br />
## 🖥️ 주요 기능
- Object Pooling을 이용한 다양한 사운드 관리
- ResourceManager을 이용한 동적 생성
- UIManager를 이용하여 다양한 팝업 관리
- DungeonManager를 이용한 스테이지, 몬스터 스폰 관리
  <br />
  <br />
    
<details>
    <summary> Manager </summary>

# 📌 Manager

## ⭐ Manager는 Singleton을 상속받아 구현


## ⚙️ GameManager.cs
> 전체적인 게임을 담당하는 매니저

1. SaveManager을 통해 게임의 데이터 저장 및 로드

<img width="740" height="311" alt="image" src="https://github.com/user-attachments/assets/e52b98d5-ede1-4a5c-8980-9fbe040a7fd8" />


2. 씬 전환에 따른 던전의 생성과 해제를 제어

<img width="745" height="160" alt="image" src="https://github.com/user-attachments/assets/8d6c61b9-3929-4c25-92ae-3d3367e934fa" />



## ⚙️ ItemManager.cs
> Item의 이동을 주로 사용, inventory와 equipment를 하나로 묶어주는 매니저

<img width="462" height="328" alt="image" src="https://github.com/user-attachments/assets/b4ae38ac-2c41-4e66-ba7e-35c8162356a9" /> <img width="462" height="328" alt="image" src="https://github.com/user-attachments/assets/de7831ef-f6cb-4f50-b0c4-42040098e4d2" />



## ⚙️ ResourceManager.cs
> Resource파일에 있는 모든 파일들을 가져와주는 매니저

파일을 불러오기위해 파일의 이름을 enum타입으로 설정

<img width="225" height="428" alt="image" src="https://github.com/user-attachments/assets/c15709bb-7d9b-4527-b5ff-23c98fa44a6a" />


동기로 데이터를 가져오는 방식과 비동기로 데이터를 가져오는 방식 두가지로 나누어 <br />
필요한 상황에 따라 데이터를 가져올 수 있도록 설계

< 비동기 >

<img width="901" height="450" alt="image" src="https://github.com/user-attachments/assets/09eeff55-fcb0-45de-a261-1cd1a64de247" />


< 동기 >

<img width="1000" height="518" alt="image" src="https://github.com/user-attachments/assets/5f224264-2080-4369-a6c7-e2cec9b8257a" />



## ⚙️ SaveManager.cs
> 데이터를 저장하고 불러올 수 있는 매니저

NewtonSoft를 사용     
<img width="187" height="63" alt="image" src="https://github.com/user-attachments/assets/689c0d14-bee5-4f91-a1e2-4ce4e7fac81e" />



<img width="672" height="252" alt="image" src="https://github.com/user-attachments/assets/edab098f-8062-4e65-bb0a-ad77098e7768" />

< 저장 >

<img width="609" height="403" alt="image" src="https://github.com/user-attachments/assets/fd951a8b-beda-4cc1-a51b-1be392e43102" />

< 불러오기 >

<img width="552" height="348" alt="image" src="https://github.com/user-attachments/assets/54ff66dc-2311-44f7-afab-236be9528039" />


## ⚙️ SoundManager.cs
> 오브젝트 풀을 활용하여, Sound를 관리해주는 매니저

<img width="710" height="400" alt="image" src="https://github.com/user-attachments/assets/ac14c159-0ca7-4adc-99cb-cb860e9b9fd2" />


paly()함수로 음악을 재생하고 음악이 끝나면 자동으로 반한되도록 설계

<img width="598" height="381" alt="image" src="https://github.com/user-attachments/assets/6565bd04-98cc-47d8-8076-ef81e83d73cb" />


< 사용법 > 


<img width="469" height="39" alt="image" src="https://github.com/user-attachments/assets/698ff98c-8517-44d0-a170-ff1540a6a867" />


## ⚙️ UIManager.cs
> UI들을 동적생성해주어 관리 할 수 있게 해주는 매니저


1. T Load<T>
캠버스를 동적으로 생성해주고, 캠버스 설정도 내부에서 진행


<img width="815" height="420" alt="image" src="https://github.com/user-attachments/assets/f8076f8f-e613-4c1e-bab3-32f409ea6c74" />


2. T Show<T>
리소스매니저에서 가져온 오브젝트 시각화

<img width="729" height="402" alt="image" src="https://github.com/user-attachments/assets/e873b17d-6440-456e-9bd3-76f2586f29be" />


< 싱글톤으로 만들어서 사용 >

<img width="299" height="25" alt="image" src="https://github.com/user-attachments/assets/428642e4-97e2-4190-a474-143d89c99396" />

</details>

<details>
    <summary> Data </summary>

# 📌 Data

## ⭐ Json을 활용하여 데이터를 가공하여 유니티에서 사용


## 📜구글 스프레드 시트에 데이터 작성
<img width="1820" height="175" alt="image" src="https://github.com/user-attachments/assets/20f64840-6ba0-43c1-914c-f96c93ea7111" />

## GSpreadSheets To Json 해서 Json파일 생성

<img width="546" height="270" alt="image" src="https://github.com/user-attachments/assets/5931111e-b5e0-4a67-8837-780297bcdea3" />

<img width="227" height="143" alt="image" src="https://github.com/user-attachments/assets/b955f0c0-5766-4049-b797-ad68fa615900" />

## C#으로 변환 ( 앞에 메타 라는 단어를 붙여 초기세팅 진행 )

<img width="381" height="573" alt="image" src="https://github.com/user-attachments/assets/6950dd2d-9fa9-4d82-b4e1-759908e8b773" />

## 유니티에서 사용할 수 있게 초기화 및 딕셔너리로 바꿔주기

1. < DataBase > 를 상속받아 초기화

<img width="465" height="256" alt="image" src="https://github.com/user-attachments/assets/9edc614d-866b-4331-a438-bc043d714a88" />


<img width="573" height="573" alt="image" src="https://github.com/user-attachments/assets/0bd0eccd-0a01-480a-9390-edbe9eea02f7" />



2. 리스트들을 딕셔너리로 사용 할 수 있게 가공

<img width="679" height="269" alt="image" src="https://github.com/user-attachments/assets/e2a727f2-00fe-447e-a0d8-06cc2ad02201" />


## ⚙️ DataBase.cs

> C#으로 바꿔준 스크립트들에게 상속시켜, 초기화 해주게 하는 코드

1. 초기화 부분

<img width="377" height="79" alt="image" src="https://github.com/user-attachments/assets/beffe44e-a715-443c-a6fe-12061ddbdcb1" />


2. 리스트화해서 딕셔너리로 바꿔주는 부분

<img width="521" height="230" alt="image" src="https://github.com/user-attachments/assets/7b44b31d-41a5-4fd8-a7fa-f1be085cfb9e" />

## ⚙️ DataManager.cs

> JSON으로 불러온 데이터를 가공시켜서 Load 해주는 매니저

<img width="1082" height="690" alt="image" src="https://github.com/user-attachments/assets/a5084468-1007-4bfc-b868-2d2f88514781" />


총 4개의 Data를 JSON으로 받아온다. ( ItemDataList, MonsterDataList, PlayerDataList, DungeonDataList )



#### T LoadData<T, M>(string resourceKey, System.Func<M, T> customAction = null) where T : new()

제너릭 메서드를 사용하여  JSON 데이터를 로드 및 반환해주는 작업, Func를 사용하여 람다식을 실행

<img width="838" height="268" alt="image" src="https://github.com/user-attachments/assets/a552e6b3-1e6c-4c9f-b6bd-df92e563b334" />


Awake에서 LoadAllData호출해서 실행된다.

<img width="278" height="249" alt="image" src="https://github.com/user-attachments/assets/36a2572e-45ef-49d5-9260-eac8a387639c" />

</details>

<details>
    <summary> Scene </summary>

# 📌 Scene

## ⭐ 씬 간의 이동, 로드, 상속 용이

## ⚙️ SceneLoadManager.cs
> 씬간의 이동을 담당하는 매니저

씬이 로딩되는 과정에서 다른 작업을 할 수 있게 Async를 사용

<img width="1221" height="346" alt="image" src="https://github.com/user-attachments/assets/d309fabd-9a1f-4683-86e5-30acf1f86e0e" />

## ⚙️ SceneBase.cs
> 모든 씬에게 상속되며, 공통적으로 필요한 매니저를 모두 넣어 현재 씬이 로드되기 전에 먼저 로드

addtive를 사용하여 씬위에 올려두었다가 지우면서 매니저들을 싱글톤에의해 재생성되는걸 방지

<img width="610" height="307" alt="image" src="https://github.com/user-attachments/assets/f36307d4-40ff-461c-94c6-4cef7d778a25" />

<img width="170" height="95" alt="image" src="https://github.com/user-attachments/assets/cda5cb5d-4326-410c-a64a-86ec234a7bc6" />

</details>

<details>
    <summary> Dungeon </summary>

<!-- summary 아래 한칸 공백 두고 내용 삽입 -->
# 📌 Dungeon

## ⭐ DB정보로 지형과 몬스터를 동적으로 생성

## ⚙️ DungeonManager.cs
> 스테이지 클리어, 해금, 던전 종료 후 리소스 정리하는 관리자 역할


1. 던전에 입장할 때 실행


   - 던전 진입 시 스테이지 데이터를 로드
   - PuzzleManager 객체를 생성하여 퍼즐들을 등록 및 관리

<img width="678" height="198" alt="image" src="https://github.com/user-attachments/assets/b07135d7-6699-42ac-9407-38ec3ad99270" />


2. DB의 스테이지 정보를 바탕으로 맵지형을 월드에 생성

   
   - 던전에 필요한 맵과 몬스터를 생성
   - stageId를 통해 로드한 데이터를 기반으로 맵 프리팹을 생성
   - spawnMonster 메서드를 사용해 몬스터를 생성 및 배치

<img width="998" height="495" alt="image" src="https://github.com/user-attachments/assets/ac9f8d36-67d6-4e57-964c-bd709cc0eb18" />


3. 문자열 파싱으로 종류와 마릿수 몬스터 생성


   - 구글 시트에서 '/'로 구분된 몬스터정보(종류, 개수)를 split하여 배열에 대입
   - 각 몬스터의 종류와 개수를 기준으로 지정된 위치에 몬스터를 생성

<img width="1148" height="823" alt="image" src="https://github.com/user-attachments/assets/7e39a3bc-d58c-4fa4-9686-21b9c563232e" />


4. 스테이지 클리어 시 연출

   - 클리어 UI를 표시
   - 다음 스테이지를 잠금 해제

<img width="678" height="421" alt="image" src="https://github.com/user-attachments/assets/b87ffdf1-4cc9-4ee6-a397-1bce29a0fc70" />




## ⚙️ MapData.cs
> 스테이지 클리어, 해금, 던전 종료 후 리소스 정리하는 관리자 역할

몬스터의 생성 위치를 제공
몬스터로 묶어 스폰 위치를 반환, 랜덤 오프셋을 적용

<img width="660" height="191" alt="image" src="https://github.com/user-attachments/assets/e82509a8-507a-457f-aa59-c33c06c89f45" />

</details>


<details>
    <summary> Tutorial </summary>

# 📌 Tutorial

## ⭐ 튜토리얼 설계

## ⚙️ TutorialBase.cs
> 튜토리얼이 시작될 때, 매 프레임마다 튜토리얼 상태 업데이트, 튜토리얼 종료 호출

<img width="532" height="346" alt="image" src="https://github.com/user-attachments/assets/d6ab8207-535a-479e-9ea9-5b8af2efe5c6" />


## ⚙️ TutorialController.cs
> TutorialBase를 상속받은 개별 튜토리얼 단계들을 리스트 순서에 따라 실행하고 관리하는 제어 클래스

초기화, 실행로직 업데이트, 다음 튜토리얼 전환, 모든 튜토리얼 완료 처리

<img width="334" height="688" alt="image" src="https://github.com/user-attachments/assets/993aaa7a-9bdd-413d-b9ad-834a29cbac29" />


## ⚙️ UIPopupTutorial.cs
> 코루틴을 활용해서 튜토리얼 가이드에 타이핑 효과를 제공
   
<img width="481" height="517" alt="image" src="https://github.com/user-attachments/assets/1745dba7-640d-471b-bc9c-4090a5bd6ad2" />


</details>


<details>
    <summary> Puzzle </summary>

<!-- summary 아래 한칸 공백 두고 내용 삽입 -->

# 📌 Puzzle

## ⭐ 튜토리얼 설계

## ⚙️ PuzzleManager.cs
> 퍼즐의 등록, 해제 및 파괴를 담당하여 메모리와 상태 데이터를 동기화

퍼즐을 리스트에 등록 / 리스트에서 해제 후 클리어 카운트 증가

<img width="370" height="309" alt="image" src="https://github.com/user-attachments/assets/52f5a1f5-d8ab-4e00-85d7-4fcac6575523" />


등록된 퍼즐 완료 확인 / 퍼즐 오브젝트 파괴 & 등록 해제

<img width="461" height="458" alt="image" src="https://github.com/user-attachments/assets/cca33656-bb8f-4a6b-aa0e-a5055858ae39" />


## ⚙️ Puzzle.cs
> 추상클래스로 구현, 공통적으로 필요한 속성 제공
쓰리매치 퍼즐에 필요한 함수 제공


1. 퍼즐 파괴 효과를 실행하고, 이펙트 파티클을 제거
<img width="419" height="119" alt="image" src="https://github.com/user-attachments/assets/80f359c9-115d-44f5-a2d7-413d372f62ea" />


2. 특정 레이어와 충돌 확인
<img width="597" height="81" alt="image" src="https://github.com/user-attachments/assets/240a51f2-7258-4525-8c1d-a543667781d2" />


3. 다른 퍼즐과 색상이 동일한지 비교
<img width="607" height="78" alt="image" src="https://github.com/user-attachments/assets/575220dc-f6f8-41c7-9208-98638ebe5965" />


</details>



<details>
    <summary> FSM </summary>

# 📌 FSM

## ⭐ Finite State Machine을 기반으로 설계된 몬스터와 플레이어

> Player의 State패턴
<img width="939" height="230" alt="image" src="https://github.com/user-attachments/assets/a5381116-d65f-4e77-afd9-b7309f8aeee5" />


> Monster의 State패턴
<img width="801" height="258" alt="image" src="https://github.com/user-attachments/assets/9d6c1daa-c545-4951-ba63-22d52a75fcd9" />


## ⚙️ StateMachine.cs
> state 패턴을 다루기 위한 기본적인 StateMachine
<img width="415" height="399" alt="image" src="https://github.com/user-attachments/assets/1789371e-eb19-4430-a2c6-b5c130e47ac6" />


## ⚙️ PlayerStateMachine.cs
> StateMachine을 상속, 개별상태를 객체화하여 관리

상태 클래스 내에서 독립적인 로직이 수행되도록 분리하여 유지보수성 향상

<img width="519" height="784" alt="image" src="https://github.com/user-attachments/assets/516ccae8-7681-4414-8207-e084df847426" />


## ⚙️ MonsterStateMachine.cs
> StateMachine을 상속, 개별상태를 객체화하여 관리

추가적으로 플레이어 타겟 인식 및 탐색, 추적 대상과 추적 상태 수행

<img width="582" height="746" alt="image" src="https://github.com/user-attachments/assets/208613bf-30f5-4c82-9a2b-ca2d78223c54" />


## ⚙️ IState.cs
> 플레이어의 각 상태가 가져야 할 생명주기(Life Cycle)를 정의한 인터페이스

<img width="252" height="132" alt="image" src="https://github.com/user-attachments/assets/f317bf53-8cf4-4a4f-aea7-b6f49b96c7ed" />

Player와 Monster 상속

<img width="450" height="450" alt="image" src="https://github.com/user-attachments/assets/10919e31-540c-4910-a4ce-ba07a2d85dc8" /><img width="400" height="400" alt="image" src="https://github.com/user-attachments/assets/30f19412-d95a-42db-b198-7428283bba26" />


</details>

<details>
    <summary> Player </summary>
 
# 📌 Player

## ⭐ 게임을 진행에 필요한 주인공!

## ⚙️ Player.cs
> 캐릭터 행동을 제어, 아이템 및 레벨업 시스템과 연동

1. 스스로 로직을 돌리지 않고 상태 머신에 위임 
  <img width="583" height="349" alt="image" src="https://github.com/user-attachments/assets/da808feb-e329-49f1-88dc-6f78acd1a91b" />


2. 아이템에 따른 스탯 동적 변경
   아이템 시스템과 연동되어 능력치가 변화
  <img width="445" height="442" alt="image" src="https://github.com/user-attachments/assets/84c6a6ec-9fee-42f9-908d-5cee738781f6" />


3. 공격
   
   - Arrow
   기본 공격
     
   <img width="624" height="181" alt="image" src="https://github.com/user-attachments/assets/43642690-d1e9-4e8d-b829-a184ac02e4c5" />
   
   - Metor
   단위 공격

   <img width="900" height="444" alt="image" src="https://github.com/user-attachments/assets/c2125ba3-1d16-426d-a008-b4eba8d5d28a" />

   - Healing
   체력 회복

   <img width="785" height="385" alt="image" src="https://github.com/user-attachments/assets/1522f4f3-2b79-442c-a20a-d55123643679" />

   - Rain
   범위 공격

   <img width="932" height="666" alt="image" src="https://github.com/user-attachments/assets/7e73aeec-d87e-4430-ba6d-cc74c1137394" />

</details>

<details>
    <summary> Monster </summary>
 
# 📌 Monster

## ⭐ 플레이어를 공격하는 다양한 몬스터

## ⚙️ Monster.cs
> DB에서 몬스터의 스탯을 자동으로 로드

1. 오브젝트 이름만으로 DB와 연동
   이름에서 (Clone) 및 숫자를 제거 후 DB키를 생성 후 적용
   
   <img width="653" height="477" alt="image" src="https://github.com/user-attachments/assets/a3f8d8d9-f1e4-41df-9082-65e08c1b2624" />

2. 몬스터 피격 및 보상처리
   
   <img width="552" height="424" alt="image" src="https://github.com/user-attachments/assets/5afc1ad0-7533-4e53-bfa2-7ecfa4fc9747" />


## ⚙️ Boss
> 보스 몬스터, 고유의 스킬 보유

- BigBlink
  
<img width="298" height="313" alt="image" src="https://github.com/user-attachments/assets/3ae376c6-7659-4daa-b572-299563f72ff7" />
<img src="https://github.com/user-attachments/assets/a421aae1-1a25-4304-8981-f4a1d4bc298a" />


- Wreck
  
<img width="600" height="300" alt="image" src="https://github.com/user-attachments/assets/4e528a15-39d5-4feb-988e-bb80ed6b777e" />
<img src="https://github.com/user-attachments/assets/e4fbd135-b557-42d9-88a7-fea406a98bda" />


- 보스의 경우 스킬 보유
  
  - BigBlink 스킬 = 에너지 볼 발사
    
    <img width="765" height="805" alt="image" src="https://github.com/user-attachments/assets/235d234c-2033-4ac2-81bc-d6b7d57b0a19" />


  - Wreck 스킬 = 배치기 + 독 공격
    
    <img width="551" height="725" alt="image" src="https://github.com/user-attachments/assets/1b5e7826-12ac-408f-a9d7-653bcf0c9332" />



## ⚙️ Normal
> 일반 몬스터, 다양한 종류

- Cyclops
  
  <img width="197" height="235" alt="image" src="https://github.com/user-attachments/assets/bd354bbf-c96a-4cc4-95fc-12ae212fd556" />


- OneEye
  
  <img width="177" height="285" alt="image" src="https://github.com/user-attachments/assets/4fec4014-61cb-4e80-bac5-5135fe018cbc" />


- Spike
  
  <img width="242" height="267" alt="image" src="https://github.com/user-attachments/assets/9d2da59b-d202-4ab8-9083-603218a0a918" />


- Wheel
  
  <img width="233" height="228" alt="image" src="https://github.com/user-attachments/assets/d70b905a-3c29-4cb0-a504-b3d1479fa54f" />


 - 일반몬스터의 경우 어택파츠가 존재
   
   어택파츠 : 공격 판정을 발생시키는 특정 신체부위나 무기 오브젝트

   <img width="634" height="575" alt="image" src="https://github.com/user-attachments/assets/772d01f6-122e-494d-8705-cca532366f96" />

 

</details>



## 📖사용 에셋
- 플레이어
  > https://assetstore.unity.com/packages/3d/characters/humanoids/fantasy/stylized-little-hero-mage-287185
- 몬스터 & 보스
  > https://assetstore.unity.com/packages/3d/characters/creatures/aliens-ultimate-pack-01-cute-series-254708
- 환경
  > https://assetstore.unity.com/packages/3d/environments/platformer-11-space-low-poly-asset-pack-by-ithappy-294367
- 파티클
  > https://assetstore.unity.com/packages/vfx/particles/epic-toon-fx-57772?clickref=1101lzYsLj7R&utm_source=partnerize&utm_medium=affiliate&utm_campaign=unity_affiliate
- 이미지
    > chat gpt의 Dall-e 모델 사용
- 사운드
  - 배경음
    > https://m.youtube.com/channel/UCsIPykZ5ilgn08vcOhmlHQQ ( 문의: sgkim10@naver.com )
  - 효과음
    > https://assetstore.unity.com/publishers/27610

    > https://assetstore.unity.com/packages/audio/sound-fx/free-casual-game-sfx-pack-54116

    > https://assetstore.unity.com/packages/audio/sound-fx/free-sound-effects-pack-155776
    




## 👨‍👩‍👧‍👧 팀원 소개
|역할|이름|깃허브|
|---|---|:---|
|팀장|홍신영|https://github.com/Hongshinyoung
|부팀장|차승민|https://github.com/SnowRabbit28
|팀원|박찬형|https://github.com/pchanbro
|팀원|임찬|https://github.com/limchaneeee
