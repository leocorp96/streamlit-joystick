# streamlit-joystick

This component wraps [nipplejs](https://www.npmjs.com/package/nipplejs), an open-source joystick library by Yoann Moinet, licensed under the [MIT License](https://github.com/yoannmoinet/nipplejs/blob/master/LICENSE).

## Installation instructions 

```sh
pip install streamlit-joystick
```

## Usage instructions

### Single Joystick
```python
import streamlit as st

from st_joystick import st_joystick

value = st_joystick()
st.write(value)
```

### Multiple Joysticks
```python
import streamlit as st

from st_joystick import st_joystick

@st.fragment
def left_joystick():
    value = st_joystick(options={'size': 200}) # default joystick id for the zone element = 0
    st.write(value)

@st.fragment
def right_joystick():
    value = st_joystick(options={'size': 200}, id=1) #remember to set the zone element id for subsequent joysticks
    st.write(value)

def main():
    cols = st.columns(2)
    with cols[0]:
        left_joystick()
    with cols[1]:
        right_joystick()


if __name__ == "__main__":
    main()
```
