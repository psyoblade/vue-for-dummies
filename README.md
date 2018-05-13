# Vue.js for dummies

## 설치 및 개발환경
### Node.js - https://nodejs.org/en/
```bash
$> node --version
```
### Npm - https://www.npmjs.com/get-npm 
```bash
$> brew install npm
```
### Visual studio code - https://code.visualstudio.com
```install plugins
* View in Browser
* HTML Snippets
* JS-CSS-HTML
* Vue 2 Snippets
* Vue-beautify
* ESLint
* vetur
```
### Chrome + vue.js devtools 
### Vue-cli
```bash
$> npm install -g vue-cli
$> npm init simple my-simple-vuejs
```

## Vue 디렉티브
### v-text, {{ }} : innerText 값에 binding. 단, html parsing 하지 않으므로 tag 입력을 그대로 할 수 있음
### v-html : innerHtml 값에 binding
### v-bind : js 변수를 html 속성 값에 binding
### v-bind:value=”message” : var message 변수를 현재 element의 value 값에 binding, v-bind:value 표현은 :value 와도 동일함
### v-model : html 입력 값을 js 변수에 apply
```html
<input type=”text” v-model=”message”> <br/> 입력 값은 : <h2 v-html=”message”/>
<script>
var vue = new Vue({ data: messge })
</script>
(v-model) → js ← html (v-bind)
```
### v-if, v-for : 조건에 따라 render 결정, iteration
```html
<select>
    <option disabled="disabled" selected>Select Option</option>
    <option v-for=”(v, k, i) in items” v-bind:value=”k” v-text=”v” v-if=”value.length > 4”/>
 </select>
```
