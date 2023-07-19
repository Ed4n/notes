---
id: wwo93g4ls9z476x0e2tn21u
title: React Dynamic Component
desc: ""
updated: 1689727106291
created: 1689727104204
---

First create a component that will contain all components

```javascript
import AdminSVG from "./AdminSVG";
import CalendarSVG from "./CalendarSVG";
import StatusSVG from "./StatusSVG";
import MailSVG from "./MailSVG";
import PetSVG from "./PetSVG";
import UserSVG from "./UserSVG";
import PhoneSVG from "./PhoneSVG";
import DropDownSVG from "./DropDownSVG";
import SearchSVG from "./SearchSVG";

export default function Icon({ color, size, type }) {
  const iconType = {
    status: <StatusSVG color={color} size={size} />,
    admin: <AdminSVG color={color} size={size} />,
    calendar: <CalendarSVG color={color} size={size} />,
    mail: <MailSVG color={color} size={size} />,
    pet: <PetSVG color={color} size={size} />,
    user: <UserSVG color={color} size={size} />,
    phone: <PhoneSVG color={color} size={size} />,
    dropDown: <DropDownSVG color={color} size={size} />,
    search: <SearchSVG color={color} size={size} />,
  };
  return <>{iconType[type]}</>;
}
```

Then Create a component that will store the SVG and its props

```javascript
export default function MailSVG({ color, size }) {
  return (
    <>
      <svg
        className={`fill-${color}`}
        xmlns="http://www.w3.org/2000/svg"
        width={size}
        height={size}
        viewBox="0 0 24 24"
      >
        <path d="M12 12.713l-11.985-9.713h23.971l-11.986 9.713zm-5.425-1.822l-6.575-5.329v12.501l6.575-7.172zm10.85 0l6.575 7.172v-12.501l-6.575 5.329zm-1.557 1.261l-3.868 3.135-3.868-3.135-8.11 8.848h23.956l-8.11-8.848z" />
      </svg>
    </>
  );
}
```

Usage:

```javascript
// Assets //
import Icon from "@/assets/svg/Icon";


<h3> Date </h3>
<Icon type="dropDown" size="12" color="white" />
```
