# 针对Observable类型的返回值
 - 使用pipe接收数据
  ```
  public GenerateNumbers() : Observable<number>{
    return of(2,4,6) //Use mocked responcinstead of real http
  }

  const source$ = GenerateNumbers();
  source.pipe(map(num => num * 10).subscribe(result => console.log(result)))
  ```
