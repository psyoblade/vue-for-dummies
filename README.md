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


## Vue 꿀팁

### 수정한 Vue 정보가 webpack --watch 수행 후에도 과거의 페이지가 보일 때
* Option + Command + I : Network : Disabled cache

### 컴포넌트를 여러개 나열 했을 때에 처음 컴포넌트만 보일 때
* Component Tag 입력 시에 닫는 Tag 값을 <Tag.../> 와 같이 닫지 않고 명시적으로 <\/Tag> 와 같이 닫는다.

## Vue 디렉티브
### [hello-vue-js](https://github.com/psyoblade/vue-for-dummies/blob/master/1.basic/index.html)
* v-text, {{ }} : innerText 값에 binding. 단, html parsing 하지 않으므로 tag 입력을 그대로 할 수 있음
* v-html : innerHtml 값에 binding
### [v-bind](https://github.com/psyoblade/vue-for-dummies/blob/master/1.basic/sum.html) js 변수를 html 속성 값에 binding
 * v-bind:value=”message” : var message 변수를 현재 element의 value 값에 binding, v-bind:value 표현은 :value 와도 동일함
### [v-model](https://github.com/psyoblade/vue-for-dummies/blob/master/1.basic/model-bind.html) html 입력 값을 js 변수에 apply
```html
<input type=”text” v-model=”message”> <br/> 입력 값은 : <h2 v-html=”message”/>
<script>
var vue = new Vue({ data: messge })
</script>
(v-model) → js ← html (v-bind)
```
### [v-if, v-for](https://github.com/psyoblade/vue-for-dummies/blob/master/1.basic/v-if-for.html) 조건에 따라 render 결정, iteration
```html
<select>
    <option disabled="disabled" selected>Select Option</option>
    <option v-for=”(v, k, i) in items” v-bind:value=”k” v-text=”v” v-if=”value.length > 4”/>
 </select>
```

### [async-request](https://github.com/psyoblade/vue-for-dummies/blob/master/1.basic/async-req.html) : watch, promise, debounce, lifecycle
<img src="images/lifecycle.png"/>


## Event Handling

### [Event Reference](https://developer.mozilla.org/en-US/docs/Web/Events)
### [HTML Event Attributes](https://www.w3schools.com/tags/ref_eventattributes.asp)

### [v-on](https://github.com/psyoblade/vue-for-dummies/blob/master/2.event/event-handling.html) 이벤트 처리
```html
    <div id="example">
        <button v-on:click="alert('in-line-click')"/>
        <button v-on:click="alertMessage"/>
        <button @click="alertMessage"/>
    </div>
    <script>
        var vm = Vue({
            el: "#example",
            data: {},
            methods: {
                alertMessage: function() {
                    alert('event handling message')
                }
            }
        })
    </script>
```

## Component Composition

### [Inherited Component](https://github.com/psyoblade/vue-for-dummies/blob/master/3.component/inherited-component.html)

### [Eventbus Component](https://github.com/psyoblade/vue-for-dummies/blob/master/3.component/eventbus-component.html)