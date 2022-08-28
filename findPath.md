var obj = {
  a: {
    b: {
      c: 12
    }
  },

findPath(path) {
  const paths = path.split('.');
  let innerObj = {...obj};
  for (let i = 0; i < paths.length; i++) {
    innerObj = innerObj && innerObj[paths[i]] || undefined;
  }
  return innerObj;
}
}



console.log(obj.findPath('a.b.c')); // 12
console.log(obj.findPath('a.b')); // {c: 12}
console.log(obj.findPath('a.b.d')); // undefined
console.log(obj.findPath('a.c')); // undefined
console.log(obj.findPath('a.b.c.d')); // undefined
console.log(obj.findPath('a.b.c.d.e')); // undefined
