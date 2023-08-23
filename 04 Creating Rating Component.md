#frontend 

So, we will be creating Rating components showing stars.

Create `Rating.js` in `components` folder.

We can use default value for some props using.
```javascript
Component.defaultProps = {
	key:"value"
}
```

We can also use PropTypes for Type check for props.
```javascript
Component.propTypes = {
	propName : PropTypes.type
}
```


![[Pasted image 20230805233129.png]]


![[Pasted image 20230805233209.png]]


CSS changes in `index.js`
![[Pasted image 20230805233550.png]]

```jsx

import React from 'react'

const Rating = ({ value, text, color }) => {
  return (
    <div className="rating">
      <span>
        <i style={{ color }}
          className={
            value >= 1
              ? 'fas fa-star'
              : value >= 0.5
                ? 'fas fa-star-half-alt'
                : 'far fa-star'
          }
        ></i>
      </span>
      <span>
        <i style={{ color }}
          className={
            value >= 2
              ? 'fas fa-star'
              : value >= 1.5
                ? 'fas fa-star-half-alt'
                : 'far fa-star'
          }
        ></i>
      </span>
      <span>
        <i style={{ color }}
          className={
            value >= 3
              ? 'fas fa-star'
              : value >= 2.5
                ? 'fas fa-star-half-alt'
                : 'far fa-star'
          }
        ></i>
      </span>
      <span>
        <i style={{ color }}
          className={
            value >= 4
              ? 'fas fa-star'
              : value >= 3.5
                ? 'fas fa-star-half-alt'
                : 'far fa-star'
          }
        ></i>
      </span>
      <span>
        <i style={{ color }}
          className={
            value >= 5
              ? 'fas fa-star'
              : value >= 4.5
                ? 'fas fa-star-half-alt'
                : 'far fa-star'
          }
        ></i>
      </span>
      <span>{text && text}</span>
    </div>
  )
}

Rating.defaultProps = {
  color: '#f8e825'
}

export default Rating

```

In next video we will setup React Router for routing [[05 Implementing React Router]].