# Composition API


## Installation

```bash
yarn add @vue/composition-api
```


## Usage

#### Example 1

<vue-code>
<div slot="demo">
<comp-demo-1/>
</div>
<div slot="code">

```html
<template>
    <button ref="btn">Composition API</button>
</template>

<script>

import { ref} from "@vue/composition-api";
import { useTippy } from "vue-tippy";

export default {
   setup(){
       const btn = ref(null)
       
       useTippy(btn, {
           content : "Cool!"
       })

       return {
           btn
       }
   }
    
}
</script>
```

</div>
</vue-code>


#### Example 2

<vue-code>
<div slot="demo">
<comp-demo-2/>
</div>
<div slot="code">

```html
<template>
    <div>
        <button @click="changePlace">Change option placement</button>
        <button ref="btn" >Composition API</button>
    </div>
</template>

<script>

import { ref, reactive} from "@vue/composition-api";
import { useTippy } from "vue-tippy";

export default {
   setup(){
        const btn = ref(null)
        const options = reactive({
           content : "Reactive options!",
           placement: 'left'
        })

       useTippy(btn, options)

       const places = ['left','top','right','bottom']
       
       const changePlace = () => {
           options.placement = places[ parseInt(Math.random() * 100) % places.length ]
       }

       return {
           btn,
           options,
           changePlace
       }
   }
    
}
</script>
```

</div>
</vue-code>

#### Example 3

<vue-code>
<div slot="demo">
<comp-demo-3/>
</div>
<div slot="code">

```html
<template>
    <div>
        <button ref="btn">Composition API</button>
        
        <div ref="content">
            WHAAAT!
        </div>
    </div>
</template>

<script>

import { ref} from "@vue/composition-api";
import { useTippy } from "vue-tippy";

export default {
   setup(){
       const btn = ref(null)
       const content = ref(null)
       
       useTippy(btn, {
           content
       })

       return {
           btn,
           content
       }
   }
    
}
</script>
```

</div>
</vue-code>
