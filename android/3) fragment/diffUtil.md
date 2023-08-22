# DiffUtil이란?
RecyclerView를 사용하면 데이터가 동적으로 바뀌는 경우 우린,<br>
notifyDataSetChanged() 한 줄로 리사이클러뷰를 갱신하곤 했다.<br>
만약 item 딱 하나만 바뀌는 경우더라도 **리스트를 전부지우고 객체를 하나하나만들기 때문에 성능면에 있어서 비효율** 적이다.<br>
따라서 **이전 데이터 상태와 현재 데이터간의 상태 차이를 계산**하고, <br>
반드시 업데이트해야 할 **최소한의 데이터에 대해서만 갱신**하게 되는<br>
DiffUtil Class를 사용할수 있다,DiffUtil은 데이터 업데이트 횟수를 최소한으로 가져갈수 있다.

## DiffUtil 사용법

DiffUtil이 **원래 목록과 새로 들어온 목록간의 차이를 계산**한뒤 **DiffUtil.Callback**이라는 추상클래스를<br>
CallBack Class로 사용한다. 이때 DiffUtil.Callback은 **4개의 추상매서드**와 **1개의 일반매서드**로 구성되어 있다.<br>
### 추상클래스 DiffUtil.Callback 의 매서드

#### 추상매서드
- getOldListSize()<br>
  기존목록의 크기를 반환한다.
- getNewListSize()<br>
  새로운목록의 크기를 반환한다.
- areItemsTheSame(int oldItemPosition, int newItemPosition)<br>
  두 아이템이 같은 객체인지 여부를 반환한다.
- areContentsTheSame(int oldItemPosition, int newItemPosition)<br>
  두 아이템이 같은 데이터를 갖고 있는지 여부를 반환한다. areItemsTheSame() 이 true 를 반환할 때만 호출된다. 애초에 객체가 다르다면 데이터를 비교하는 것은 의미가 없기 때문이다.

#### 일반매서드
- getChangePayload(int oldItemPosition, int newItemPosition)<br>
  만약 areItemTheSame()이 true를 반환하고, areContentsTheSame()이 false를 반환했다면 새로운 녀석이 들어왔다는 것으로 간주하고 해당 메소드가 호출되어 변경 내용에 대한 페이로드를 가져온다. 해당 메소드는 추상 메소드가 아니기 때문에 꼭 오버라이드할 필요는 없다.