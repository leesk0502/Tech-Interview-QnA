[Back to Contents](../README.md)
# Algorithm Interview QnA
알고리즘 면접 질문과 답

### Q1. 배열 뒤집기
```
void reverse(int *arr, int size){
  for(int i=0; i<size/2; i++){
    int temp = arr[i];
    arr[i] = arr[(size-1) - i];
    arr[(size-1) - i] = temp;
  }
}
```

### Q2. 숫자 문자열을 정수로 만들기(atoi 구현)
```
int atoi(char *c){
  int value = 0;
  int positive = 1;

  if(*c = '\0') return 0;
  if(*c == '-') positive = -1;

  while(*c){
    if( *c > '0' && *c < '9' ){
      value = value * 10 + (*c - '0');
    }
    c++;
  }

  return value * positive;
}
```

### Q3. 1~100 숫자가 들어있는 1억 사이즈 배열 중앙값 찾기
```
float median(vector<int> &arr){
  sort(arr.begin(), arr.end());

  if(arr.size() % 2 == 1){
    return (float)arr[arr.size() /2 ];
  }
  else {
    return ((float)arr[arr.size() / 2] + (float)arr[arr.size() / 2 + 1) / 2.0f;
  }
}
```

### Q4. 버블 소트 구현
```
void bubble_sort(vector<int> &v){
  for(int i=0; i<v.size() - 1; i++){
    for(int j=1; j<v.size() - 1; j++){
      if(v[j-1] < v[j])
        swap(v[j-1], v[j]);
    }
  }
}
```

### Q5. 선택 정렬 구현
```
void selection_sort(vector<int> &v){
  for(int i=0; i<v.size() - 1; i++){
    int tmp = i;
    for(int j=i+1; j<v.size(); j++){
      if(v[tmp] >= v[j]) tmp = j;
    }

    swap(v[i], v[tmp]);
  }
}
```

### Q6. 삽입 정렬 구현
```
void insertion_sort(vector<int> &v){
  for(int i=1; i<v.size(); i++){
    int key=v[i];
    j = i-1;
    while(j >= 0 && key < v[j]){
      swap(v[j], v[j+1]);
      j--;
    }
    v[j+1] = key;
  }
}
```

### Q7. 퀵 소트 구현
* 재귀 구현
```
void three_sort(vector<int> &v, int front, int mid, int rear){
  if(v[front] > v[mid]) swap(v[front], v[mid]);
  if(v[mid] > v[rear]) swap(v[mid], v[rear]);
  if(v[front] > v[mid]) swap(v[front], v[mid]);
}
void quick_sort(vector<int> &v, int front, int rear){
  int i, j, pivot, mid = front + (rear - front)/2;
  three_sort(v, front, mid, rear);

  if(rear-front+1 > 3){
    pivot = v[mid];
    swap(v[mid], v[rear-1]);
    i = front;
    j = rear - 1;
    while(true){
      while(v[++i] < pivot && i < rear);
      while(v[--j] > pivot && front < j);
      if(i >= j) break;
      swap(v[i], v[j]);
    }
    swap(v[i], v[rear-1]);
    quick_sort(v, front, i-1);
    quick_sort(v, i+1, rear);
  }
}
```

* 비재귀
```
void quick_sort(vector<int> &v, int front, int rear){
  push(rear);
  push(front);

  while(!emprt(stack)){
    front = pop();
    rear = pop();
    if(rear - front > 0){
      int pivot = v[rear];
      int i = front - 1;
      int j = rear;
      while(true){
        while(v[++i] < pivot);
        while(v[--j] > pivot);
        if(i > j) break;
        swap(v[i], v[j]);
      }
      swap(v[i], v[rear]);
      push(rear);
      push(i + 1);
      push(i - 1);
      push(front);
    }
  }
}
```
