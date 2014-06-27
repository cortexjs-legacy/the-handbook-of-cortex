# About cortex.json

Most of the fields in cortex.json is similar to `npm`'s package.json.

It is important to know the meaning of each field.

##name

This is the most important field, it specifies the package name, which is the unique identifier of a package.

## version

The version of the package. Changes to the package should always come along with changes to the version.

## description

It helps people to know what is this package about.

## keywords

It's an array of strings, always put some keywords here, and it will helps people to discover the package while searching

## homepage

The project homepage

## repositry

The project repositry, like:
```
"repository": "git://github.com/cortexjs/cortexjs-www.git"
```


## bugs

The bugs report page, like this:
```
"bugs": {
    "url": "http://github.com/cortexjs/cortexjs-www/issues"
 }
```

## license
The project license

## author, contributors
The "author" is one person. "contributors" is an array of people. A "person" is an object with a "name" field and optionally "url" and "email", like this:

```
{
    "name": "ltebean",
    "email": "yucong1118@gmail.com"
}
```

## main
The entry point of a package, it's modules.exports will be returned when calling `require('packageName')`.





