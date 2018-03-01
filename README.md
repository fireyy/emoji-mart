>## This Project Is Deprecated. Use [emoji-mart-vue](https://github.com/jm-david/emoji-mart-vue) instead.

<div align="center">
  <br><b>Vue Emoji Mart</b> is a Slack-like customizable<br>emoji picker component for Vue, inspired by [Emoji Mart](https://github.com/missive/emoji-mart).
  <br><a href="https://missive.github.io/emoji-mart">Demo</a> • <a href="https://github.com/missive/emoji-mart/releases">Changelog</a>
  <br><img src="https://cloud.githubusercontent.com/assets/436043/17186519/9e71e8fe-5403-11e6-9314-21365c56a601.png">
  <br><a title="Team email, team chat, team tasks, one app" href="https://missiveapp.com"><img alt="Missive | Team email, team chat, team tasks, one app" src="https://cloud.githubusercontent.com/assets/436043/17186909/17f9cede-5405-11e6-988a-a7c2380af396.png"></a>
  <br>Brought to you by the <a title="Team email, team chat, team tasks, one app" href="https://missiveapp.com">Missive</a> team
</div>

## Installation

`npm install --save vue-emoji-mart`

## Components
### Picker
```html
<template>
  <div>
    <Picker
      :emoji-size="emojiSize"
      :per-line="perLine"
      :skins="skin"
      :native="native"
      :set="set"
      :auto-focus="autoFocus"
      :include="include"
      :exclude="exclude"
      :onItemClick="insertSymbol"
    />
  </div>
</template>
<script>
import 'vue-emoji-mart/css/emoji-mart.css'
import { Picker } from 'vue-emoji-mart'

export default {
  data () {
    return {
      emojiSize: 24,
      perLine: 9,
      skin: 1,
      native: true,
      set: 'apple',
      hidden: false,
      currentEmoji: { id: '+1' },
      autoFocus: false,
      include: [],
      exclude: [],
    }
  },
  methods: {
    insertSymbol (emoji) {
      console.log(emoji)
    }
  }
}
</script>
```

| Prop | Required | Default | Description |
| ---- | :------: | ------- | ----------- |
| **autoFocus** | | `false` | Auto focus the search input when mounted |
| **color** | | `#ae65c5` | The top bar anchors select and hover color |
| **emoji** | | `department_store` | The emoji shown when no emojis are hovered, set to an empty string to show nothing |
| **include** | | `[]` | Only load included categories. Accepts [I18n categories keys](#i18n). Order will be respected, except for the `recent` category which will always be the first. |
| **exclude** | | `[]` | Don't load excluded categories. Accepts [I18n categories keys](#i18n). |
| **custom** | | `[]` | [Custom emojis](#custom-emojis) |
| **emojiSize** | | `24` | The emoji width and height |
| **onClick** | | | Params: `(emoji, event) => {}` |
| **perLine** | | `9` | Number of emojis per line. While there’s no minimum or maximum, this will affect the picker’s width. This will set *Frequently Used* length as well (`perLine * 4`) |
| **i18n** | | [`{…}`](#i18n) | [An object](#i18n) containing localized strings |
| **native** | | `false` | Renders the native unicode emoji |
| **set** | | `apple` | The emoji set: `'apple', 'google', 'twitter', 'emojione', 'messenger', 'facebook'` |
| **sheetSize** | | `64` | The emoji [sheet size](#sheet-sizes): `16, 20, 32, 64` |
| **backgroundImageFn** | | ```((set, sheetSize) => …)``` | A Fn that returns that image sheet to use for emojis. Useful for avoiding a request if you have the sheet locally. |
| **emojisToShowFilter** | | ```((emoji) => true)``` | A Fn to choose whether an emoji should be displayed or not |
| **skin** | | `1` | Default skin color: `1, 2, 3, 4, 5, 6` |
| **style** | | | Inline styles applied to the root element. Useful for positioning |
| **title** | | `Emoji Mart™` | The title shown when no emojis are hovered |

#### I18n
```js
search: 'Search',
notfound: 'No Emoji Found',
categories: {
  search: 'Search Results',
  recent: 'Frequently Used',
  people: 'Smileys & People',
  nature: 'Animals & Nature',
  foods: 'Food & Drink',
  activity: 'Activity',
  places: 'Travel & Places',
  objects: 'Objects',
  symbols: 'Symbols',
  flags: 'Flags',
  custom: 'Custom',
}
```

## Development
```sh
$ yarn run build:data
$ yarn start
$ open example/index.html
```

## 🎩 Hat tips!
Powered by [iamcal/emoji-data](https://github.com/iamcal/emoji-data) and inspired by [iamcal/js-emoji](https://github.com/iamcal/js-emoji).<br>
🙌🏼  [Cal Henderson](https://github.com/iamcal).

<br><br>
<div align="center">
  <a title="Team email, team chat, team tasks, one app" href="https://missiveapp.com"><img alt="Missive | Team email, team chat, team tasks, one app" src="https://cloud.githubusercontent.com/assets/436043/17222476/7fb2ef62-54c6-11e6-81a9-6b9d7323d19c.png"></a>
  <br><a title="Team email, team chat, team tasks, one app" href="https://missiveapp.com">Missive</a> mixes team email and threaded group chat for productive teams.
  <br>A single app for all your internal and external communication and a full work management solution.
</div>
