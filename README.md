# HTML injector
Helps inject a vue.js component to certain place in v-html string

# Usage
Import:
`npm i vue-html-injector`
```javascript
import injector from 'vue-html-injector/main.vue'
export default {
  components: {
    injector
  }
}
```
Raw HTML
```
<p>Lorem ipsum dolor sit amet, consectetur adipisicing elit,</p>  
%%default%%
<p>ed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</p>
```
Injector component with HTML prop "content"
```javascript
<injector :content="rawHTML">
  <p>{{ new Date().getFullYear() }}</p>
</injector>
```

#Multiple slots:

Raw HTML
```
<p>Lorem ipsum dolor sit amet, consectetur adipisicing elit,</p>  
%%image%%
<p>ed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</p>
%%hr%%
```
Injector component with HTML prop "content"
```javascript
<injector :content="rawHTML">
  <template slot="image">
    <image-component src="logo.png" />
  </template>
  <template slot="hr">
    <hr />
  </template>
</injector>
```
