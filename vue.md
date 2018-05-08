# 组件文件

## 组件分成单独文件

## 组件名优先用 PascalCase，其次用 kebab-case

## 组件名必需多单词

## 组件命名要语义化，要使用合适的单词，不要拼错单词

## 使用完整单词，尽量不要用单词缩写，尤其不要自己创造缩写

## 组件名使用多级前缀，少使用多级目录

## 抽象基础组件，并给基础组件名加统一的前缀

## 单例组件使用前缀 The

## 单文件组件的顶层标签顺序 template, script, style

## 文件内容，每一级缩进使用 2个空格，不允许使用 tab键

## 父子元素通信，必需使用prop和event，不能使用$parent或修改prop

## 使用vuex管理数据

# 单文件组件的 template 部分

## template标签的下一级开始缩进
<template>
  <div class="work-detail">
  </div>
</template>

## 如果 元素有多个属性，每个属性一行，结尾的 > 单独一行并且与 开头的 < 对齐

## 属性值必需用双引号

## 属性值如果是js代码，js代码中的字符串用单引号

## v-for 与 v-if 避免用在同一个元素

## 使用 v-for 时，如果没有特殊需要，必需同时使用 key

## v-if / v-else-if / v-else 的元素类型相同，必需使用 key

## v-bind:xxx 全部缩写为 :xxx

## v-on:xxx 全部缩写为 @xxx

## template 中只能包含简单直接的js代码，否则必需把逻辑提取到script部分，例如使用 计算属性 或 函数 或 过滤器
看代码时需要停顿下来分析代码的逻辑，就不算是简单的代码。

## 自定义组件的元素使用 PascalCase 
如 <XxxButton/>

## 没有内容的自定义组件，使用自闭合的标签
如 <XxxButton/>

## 在template中自定义组件的prop，使用 kebab-case
如 <XxxButton current-state="x"/>

## 元素的属性按如下顺序排列
> 定义
is

> 列表渲染
v-for

> 添加渲染
v-if
v-else-if
v-else
v-show
v-cloak

> 渲染方式
v-pre
v-once

> 全局感知
v-id

> 唯一特性
ref
key
slot

> 双向绑定
v-model

> 单向绑定
v-bind

> 其它属性

> 事件
v-on

> 内容
v-html
v-text

# 单文件组件的 script 部分

## script标签的下一级不缩进
<script>
import api from '@/api/index';

export default {
  name: 'work-detail'
}
</script>

## 组件名使用 PascalCase

## 如果不是单例组件，data 必需是返回一个对象的函数

## prop定义时，名称使用 camelCase
prop的名称，定义时使用 camelCase，在template中使用时用kebab-case

## prop定义至少要指定数据类型，最好尽量详细，例如定义 默认值，是否必需，数据验证规则等

## 函数名要语义化，要使用合适的单词，不要拼错单词

## 每个计算属性和函数尽量简单
简单的函数更容易理解和维护。把复杂的函数拆成简单的小函数，不一定是为了复用，可以只是为了提高可读性。

## 需要在多个组件中复用的工具函数，集中到一个工具类中，或定义为 filter，不要再每个组件重复定义
例如时间格式化，文件大小格式化。

## 组件选项的顺序

name
props
data
computed
watch
生命周期钩子
methods
filters

# 单文件组件的style部分

##style标签的下一级不缩进
<style lang='stylus' scoped>
@import '../../assets/style/common/var.styl';

.work-detail
  display: flex;
</style>

## 使用stylus语言
<style lang='stylus' scoped>
</style>

## 不要使用花括号

## 冒号后加一个空格

## class名与上一行的 css规则，之间加一个空行
<style lang='stylus' scoped>
.work-detail
  display: flex;

  .work-info
    width: 30%;
</style>

## 使用 scoped特性 或 CSS Modules
<style scoped>
</style>

<style module>
</style>

## 为class设置适当的前缀，避免与外部class冲突
<style lang='stylus' scoped>
.m-bar
  // 同 .m-bar__btn，不要直接用 btn 作为class名
  &__btn
    position: relative;
</style>

## 不要使用元素选择器，必需使用类选择器（即定义class）









