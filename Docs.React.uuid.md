---
id: f5ubnbws05v4wrl531kkug3
title: uuid
desc: ""
updated: 1690412585198
created: 1690412212373
---

A UUID (Universal Unique Identifier) is a 128-bit value used to uniquely identify an object or entity on the internet. Depending on the specific mechanisms used, a UUID is either guaranteed to be different or is, at least, extremely likely to be different from any other UUID generated until A.D. 3400.

here is how you can generate an uuid for a test project:

```other
npm i uuid
```

now you need to import it whre you need it like this:

```javascript
import { v4 as uuid } from "uuid";
```

usage:

```javascript
const handleSubmit = (e) => {
  e.preventDefault();
  console.log(task);
  dispatch(
    addTask({
      ...task,
      // uuid usage
      id: uuid(),
    })
  );
};
```
