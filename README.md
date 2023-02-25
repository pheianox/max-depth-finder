# Max Depth Finder

This script finds the maximal depth of the DOM on the page.

## Usage

1. Copy this script
```js
((target) => {
  if (!target) return console.log('1 argument is required')
  const search = (root, iterator, depth = 0) => iterator(root, depth, [...[].map.call(root.children, child => search(child, iterator, depth + 1))])
  const maxer = (_, depth, children) => children.length ? Math.max(...children) : depth
  console.log('\n\n\nmax depth is', search(target, maxer), '\n\n\n')
})(document.body)
```
2. Go to the website and open the devtools with Ctrl+Shift+I, from there navigate to "Console" and paste the script below and press Enter to execute it

![image](https://user-images.githubusercontent.com/77569421/221371845-a580de6a-96fa-4015-8cc4-4bc9ae2f8edf.png)

3. The script will find the maximal depth using the DFS algoritm and print the result out as the output

![image](https://user-images.githubusercontent.com/77569421/221371903-636dba39-91f6-4acf-9a9e-4afe8f808dc0.png)
