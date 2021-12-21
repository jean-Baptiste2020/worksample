
> What is the correct use of "singular" and "plural" in Rails. ?

Ruby on Rails is good at doing the manual work for you. With just one line, Rails can create the model, controller, and view files associated with your application. The downside to using generate rails or its g rail shortcuts is that small errors like typos are magnified. If Rails is waiting for a user and you typed in users by mistake, it could cause functionality errors.

So this cheat sheet will help to avoid these conflicts.

- [ ] Plural:
```
    - Controller
    - Migrations/Tables
    - Routes
    - Seed Data
    - View
```

- [ ] Singular:
```
    - Model
    - Scaffold
```
