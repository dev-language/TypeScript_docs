
## Input

### onchange 타입 기본 스니펫
```jsx

const [todoInput, setTodoInput] = useState('');

const inputTodo = (event: React.ChangeEvent<HTMLInputElement>) => {
	const {
		target: { value },
	} = event; // event.target.value 와 같은 새로운 신문법이다.
	setTodoInput(value);
}
```

```jsx
<input value={todoInput} onChange={inputTodo} />
```

## TS에서의 Map 
TS에서 Map 함수를 사용할때, 반드시 key 값을 넣어줘야 한다.

```ad-info
1. React가 어떤 항목을 변경, 추가 또는 삭제할지 식별하는 것을 돕고, 
2. 엘리먼트에 안정적인 고유성을 부여하기 위해 배열 내부의 엘리먼트에 지정해야 한다.
```

```jsx
function App() {
const [todoTitle, setTodoTitle] = useState([{ id: 0, text: '밖에 나가서 해물찜 먹기', body: '노래방 가기', isdone: false }]);

<div>
  <h1>할 일</h1>
  {/*map 함수를 사용하여 바인딩을 한다*/}
  {/*map사용할때는 반드시 Key값이 들어가야한다.*/}
  {todoTitle.map((a, i) => {
    return (
      <div key={i}>
        <h3>{a.text}</h3>
        <h4>{a.body}</h4>
        <button>완료</button>
        <button>삭제</button>
      </div>
    );
  })}
</div>	
}
```

