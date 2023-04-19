# computed-bug

This repo shows a difference in reactivity behaviour in Vue 3 between dev and production

Run the repo in dev mode:
```
npm run dev
```
And observe the console as you change the selected option. Computed property `mappedValues` will be re-calculated every time, even though it depends only on a static `items` prop that remains unchanged. Same happens if you use `watch` instead of `computed`

Now run it in preview mode:
```
npm run build
npm run preview
```

And observe that the console logs appear only once when the component is mounted.