<img width="1920" height="1080" alt="조디악" src="https://github.com/user-attachments/assets/aff01cbb-867e-43b1-9641-6b60456bac0a" />

# 프로젝트명: ZODIAC
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

## ⭐Manager는 Singleton을 상속받아 구현


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


동기로 데이터를 가져오는 방식과 비동기로 데이터를 가져오는 방식 두가지로 나누어

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

## ⭐Json을 활용하여 데이터를 가공하여 유니티에서 사용할 수 있게 한다.

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

## ⭐씬 이동을 위한 SceneLoadManager와 씬마다 SceneBase를 상속

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
📌 Dungeon
⭐ DungeonManager
   ## ⚙️ SceneBase.cs // 던전관련 매니저 올리기
   
![스크린샷 2025-01-20 오후 2 44 51](https://github.com/user-attachments/assets/5af45c05-c089-45cf-914f-2426a66751a0)

InitializeDungeon(string stageId, int starIndex, int stageIndex)
던전에 입장할 때 실행되는 메서드입니다.
PuzzleManager 객체를 생성하여 퍼즐들을 등록 및 관리합니다.
매개변수로 받은 stageId를 활용해 던전 데이터를 로드합니다.

![스크린샷 2025-01-20 오후 3 17 13](https://github.com/user-attachments/assets/477554fb-b3f7-4787-88e9-0a3f50b55753)

SpawnStageObjects(string stageId, MetaDungeonData stageData)
던전에 필요한 맵과 몬스터를 생성합니다.
stageId를 통해 로드한 데이터를 기반으로 맵 프리팹을 생성합니다.
spawnMonster 메서드를 사용해 몬스터를 생성 및 배치 해줍니다.

![스크린샷 2025-01-20 오후 3 19 09](https://github.com/user-attachments/assets/7023ec77-ebcc-44c7-a0b9-ee90af9bedc7)

SpawnMonster(string SpawnMonster, string MonsterCount, MapData mapData)
구글 시트에서 ‘/‘로 구분된 몬스터정보(종류, 개수)를 split하여 배열에 넣어줍니다.
각 몬스터의 종류와 개수를 기준으로 지정된 위치에 몬스터를 생성합니다.

![스크린샷 2025-01-20 오후 3 20 43](https://github.com/user-attachments/assets/aab90033-823f-4702-a762-752d54fe8f7c)

StageClear()
스테이지를 클리어했을 때 호출됩니다.
클리어 UI를 표시합니다.
다음 스테이지를 잠금 해제합니다.

2. MapData

![스크린샷 2025-01-20 오후 2 44 05](https://github.com/user-attachments/assets/bf596f39-0b94-4d9f-b528-22d3fc908c4d)

몬스터의 생성 위치를 제공합니다.

GetMonsterSpawnPoint(int index)
같은 종류의 몬스터로 묶어 스폰 위치를 반환하며, 랜덤 오프셋을 적용합니다.
</details>


<details>
    <summary> Tutorial </summary>

<!-- summary 아래 한칸 공백 두고 내용 삽입 -->

1. TutorialBase
   
![스크린샷 2025-01-20 오후 3 22 14](https://github.com/user-attachments/assets/d697bea5-8388-4d9f-bc5c-4776c5d47875)

abstract void Enter()
튜토리얼이 시작될 때 호출합니다.

abstract void Execute(TutorialController controller)
매 프레임마다 튜토리얼 상태를 업데이트합니다.

abstract  void Exit()
튜토리얼이 종료될 때 호출됩니다.

2. TutorialController
   
![스크린샷 2025-01-20 오후 3 22 48](https://github.com/user-attachments/assets/29a004e8-11f3-472c-a3d2-54d36d4522b1)

void Start()
첫 번째 튜토리얼을 초기화 합니다.

void Update()
현재 튜토리얼의 실행 로직을 업데이트합니다.

void SetNextTutorial()
다음 튜토리얼로 전환하거나, 모든 튜토리얼을 완료 처리합니다.

void CompletedAllTutorials()
모든 튜토리얼이 완료된 후 실행될 로직을 처리합니다.

3. UIPopupTutorial
   
![스크린샷 2025-01-20 오후 3 25 29](https://github.com/user-attachments/assets/e2a923c3-ca5e-45ea-98a2-dc6f3987361d)

SetTutorialData(string text)
UI팝업을 활성화하고, 튜토리얼 메세지를 설정하고 출력 애니메이션을 시작합니다.

ShowTutorialText(string text, float delay)
입력받은 텍스트를 한 글자씩 설정한 delay 간격으로 출력합니다.
</details>


<details>
    <summary> Puzzle </summary>

<!-- summary 아래 한칸 공백 두고 내용 삽입 -->

1. PuzzleManager
   
![스크린샷 2025-01-20 오후 3 28 43](https://github.com/user-attachments/assets/932045a0-3517-4d68-93a7-4de60889b2eb)

RegisterPuzzle(Puzzle puzzle)
퍼즐을 리스트에 등록합니다.

UnregisterPuzzle(Puzzle puzzle)
퍼즐을 리스트에서 해제하고 클리어 카운트를 증가합니다.

AreAllPuzzlesCompleted()
등록된 모든 퍼즐이 완료되었는지 확인합니다.

DestroyPuzzles(IEnumerable<Puzzle> puzzles)
퍼즐 오브젝트를 파괴하고 등록을 해제합니다.

2. Puzzle(추상클래스)
모든 퍼즐은 이 클래스를 상속받아 구현되며, 공통적으로 필요한 퍼즐 완료 여부, 퍼즐의 초기 위치, 퍼즐의 색상, 퍼즐이 충돌가능한 레이어 마스크 등의 속성을 제공합니다.

![스크린샷 2025-01-20 오후 3 27 23](https://github.com/user-attachments/assets/717019c1-fc7a-4e16-8468-112d9f579901)

Start()
퍼즐을 PuzzleManager 리스트에 등록합니다.

OnDestroy()
퍼즐 파괴 시 PuzzleManager에서 등록을 해제합니다.

PlayDestroyEffect(Vector3 position)
퍼즐 파괴 효과를 실행하고, 이펙트 파티클을 제거합니다.

IsCollisionWithLayer(GameObject obj, LayerMask layerMask)
특정 레이어와 충돌을 확인합니다.

IsSameColor(Puzzle otherPuzzle)
다른 퍼즐과 색상이 동일한지 비교합니다.

</details>



<details>
    <summary> FSM </summary>

  - FSM: Finite State Machine을 기반으로 설계된 몬스터와 플레이어
  > 몬스터와 플레이어는 FSM패턴을 기반으로 설계되었다.
  - Player의 State패턴<br>
    ![image](https://github.com/user-attachments/assets/16e39d59-4c2e-4971-95bc-c30ea6834bff)<br>
  - Monster의 State패턴<br>
    ![image](https://github.com/user-attachments/assets/f455eb03-e1d3-4a3c-a3da-0b9706ddc809)<br>
  - 코드 예시<br>
    - StateMachine<br>
    state패턴을 다루기 위한 기본적인 StateMachine<br>
    ![image](https://github.com/user-attachments/assets/2f918887-a4a2-4515-b652-f66b71ffc6ae)<br>
    - StateMachine을 상속받은 PlayerStateMachine과 MonsterStateMachine<br>
    ![image](https://github.com/user-attachments/assets/69d061dc-0872-4223-90ec-b622057b8d64)<br>
    ![image](https://github.com/user-attachments/assets/47d6867a-d6c3-4d3d-88fb-c8d8323b279f)<br>
    - State<br>
    ![image](https://github.com/user-attachments/assets/76fb7737-a3bf-4123-ac46-d2032ea042ae)<br>    
    각 State들은 인터페이스 IState를 상속받아 필수적인 요소들을 구현하면 된다.<br>    
    예시로 Player와 Monster의 State를 하나씩 보면<br>
    플레이어의 모든 상태의 근원이 되는 BaseState, 플레이어의 키 입력을 받아 움직임을 조절하는 컨트롤러 메서드와 애니메이션을 다루는 메서드가 존재한다.<br>
    ![image](https://github.com/user-attachments/assets/bd8e3b5f-044d-47ea-aed7-206b239a0de9)<br>
    몬스터의 모든 상태의 근원인 BaseState, 애니메이션과 움직임, 캐릭터와의 거리 체크 등의 메서드가 존재한다.<br>
    ![image](https://github.com/user-attachments/assets/804e37f3-ea43-44b2-9c87-108d4a18b82a)<br>  

</details>

<details>
    <summary> Player </summary>
 
## 플레이어
  > 기본적으로 게임을 진행하는데 주인공인 플레이어가 존재한다.
  - 플레이어 스크립트<br>
  기본적으로 크게 기능이 있는게 아니라 대부분 캐싱해서 가져온다.<br>
  ![image](https://github.com/user-attachments/assets/1771146b-728e-4825-9f92-5fad007a3119)<br>

  - 인풋액션<br>
  인풋액션을 활용해 키셋팅을 먼저 해놓고 기능을 구독해서 사용한다.
  ![image](https://github.com/user-attachments/assets/782cf929-6434-46b0-8c53-6b50eb591b0c)<br>

  - 기본공격 스크립트<br>
   마우스 왼쪽클릭으로 공격을 할수있다. Arrow는 총알의 물리적 기능을 담당하고 BasicAttack은 총알의 생성을 담당한다.
  ![image](https://github.com/user-attachments/assets/8a58cfa8-371a-432e-9aa8-6bcb8a1633cc)
  ![image](https://github.com/user-attachments/assets/156e94bc-d417-40f0-a496-b07682582e43)<br>

  - 스킬공격 스크립트<br>
    스킬 매니저는 각 스킬의 사용버튼과 사거리 부분을 담당하고, 
  
</details>

<details>
    <summary> Monster </summary>
 
## 몬스터
  > 플레이어를 공격하는 다양한 몬스터가 존재한다.
  - 몬스터 스크립트<br>
    ![image](https://github.com/user-attachments/assets/9c7d2ff2-898d-4446-b1b9-03370f7043b4)<br>
    ![image](https://github.com/user-attachments/assets/cb8f85ab-900f-4235-beaa-5f9d65681d54)<br>
    ![image](https://github.com/user-attachments/assets/3f2b324f-49ab-4f31-bffb-d28ae0375b0d)<br>
    ![image](https://github.com/user-attachments/assets/12b0d0b7-5fae-45e1-a564-9688726c0961)<br>



  - 보스 몬스터, 고유의 스킬을 가지고 있다.
    - BigBlink<br>
      ![image](https://github.com/user-attachments/assets/08291f87-73fe-4ab9-a385-6f7ccb822680)<br>
      ![몬스터 임시 제작](https://github.com/user-attachments/assets/bbe9ce33-794f-476b-8081-0cf3b7512f7e)

  - 일반 몬스터
    - Wreck<br>
      ![image](https://github.com/user-attachments/assets/33404ff3-327d-4859-b01d-be19cf957b7a) <br>
      ![](https://velog.velcdn.com/images/chant/post/cc5da6d5-3495-4ea9-a2ab-db093dfe021f/image.gif)<br>
  - 일반 몬스터
    - Cyclops<br>
    ![image](https://github.com/user-attachments/assets/53c33c2c-adca-44c2-8aaf-995aca11352d)
    - OneEye<br>
    ![image](https://github.com/user-attachments/assets/729e8922-ea16-4a18-82fc-a7b7917f0f21)
    - Spike<br>
    ![image](https://github.com/user-attachments/assets/37c6cc71-e705-4465-9e30-b870d4e3ddaf)
    - Wheel<br>
    ![image](https://github.com/user-attachments/assets/07a7b732-0f8e-47d9-ba5e-edfb5caeb32d)
  - 몬스터의 Inspector<br>
    몬스터는 기본적으로 하위 오브젝트에 몬스터 디자인 본체와 어택파츠를 가지고 있으며 보스 몬스터는 스킬도 가지고 있다.
    - 부모 오브젝트의 Inspector<br>
    ![image](https://github.com/user-attachments/assets/37b71b14-d0a5-45a4-9459-7cbce247097c)<br>
    - 본체의 Inspector<br>
    ![image](https://github.com/user-attachments/assets/de4b7283-3851-4439-9cb7-62586743ca07)<br>
    - 어택 파츠의 Inspector와 스크립트<br>
    ![image](https://github.com/user-attachments/assets/5ec9a8a2-5b06-4c30-8a35-4c907c001585)<br>
    ![image](https://github.com/user-attachments/assets/10588e91-4d3e-49df-9356-bdc00a05354c)<br>
    - 스킬의 Inspector와 스크립트<br>
    ![image](https://github.com/user-attachments/assets/a0ee6703-af6b-4439-ba3f-46077cb209c0)<br>
    ![image](https://github.com/user-attachments/assets/1b4a0c06-04df-4a24-bcc5-5fd186947fe5)<br>
    ![image](https://github.com/user-attachments/assets/09cd1c04-9932-43ab-890a-890e973d7fe8)<br>
    Skill 스크립트를 상속받아 고유의 스킬을 구현한다.<br>
    스킬 1<br>
    ![image](https://github.com/user-attachments/assets/890d4ac0-866a-455f-8a6e-1d7132fd9e3a)<br>
    스킬 2<br>
    ![image](https://github.com/user-attachments/assets/dbcd0b7f-85f3-48cd-b178-c3ae325252c2)<br>

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
