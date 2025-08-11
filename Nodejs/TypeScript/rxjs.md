# 针对Observable类型的返回值
 - 使用pipe接收数据
  ```
  import { of } from 'rxjs';
  import { map } from 'rxjs/operators';

  public GenerateNumbers() : Observable<number>{
    return of(1,2,4,6) //Use mocked responcinstead of real http
  }

  const source$ = GenerateNumbers();
  source.pipe(
    switchMap(data => this.http.get(`https://api.example.com/details/${data.id}`)),
    filter(numbers => numbers.length > 0), 
    map(numbers => numbers.filter(num => num % 2 === 0)), 
    map(numbers => numbers.map(num => num * 10)),
    tap(processedData => console.log("优化后的数据:", processedData))，
    takeUntil(this.destroy$)
    )
    .subscribe()
  ```

  filter用于筛选数据，map用于数据的处理，tap用于数据的调试,switchmap用于接口嵌套，在请求结束后调用另一个请求，takeutil用于指监听其他事件，在其他事件发生时取消该订阅。

