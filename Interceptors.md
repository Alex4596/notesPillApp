### Kod pre rozsirenie Schopnosti HttpClientu v angulari

##### Cli kod: `ng g interceptor <Route>.interceptor`
- pozor na `ng g i` = vytvori interface

```
export const authInterceptor: HttpInterceptorFn = (req, next) => {
  const authToken = 'your-token-here';
  
  const authReq = req.clone({
	setHeaders: { Authorization: `Bearer ${authToken}` }
  });
  return next(authReq);
};
```

### !POZOR Interceptor musime zapisat do app.config aby sa aplikoval
```
export const appConfig: ApplicationConfig = {
  providers: [
    provideHttpClient(
      withInterceptors([authInterceptor])
    )
  ]
};
```

### Mozeme pouzit RxJS kniznicu pri pisani Interceptorov