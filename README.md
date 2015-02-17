# md-chips
Angular input-chips directive following Google Material Design guidelines

## Dependencies
This directive works with Angular v1.3.13. 

## Loading

In your html code include mdchips.js and md-chips.css

```html
<link rel="stylesheet" type="text/css" href="mdchips.css">

<script src="mdchips.js"></script>
```

Then you only need to require mdChips module as a dependency 

```javascript
angular.module('myModule', ['mdChips'])
```

## Usage

In your html markup write

```javascript
<md-chips collection='itemsCollection' ng-model='selectedUsers' md-title='title' md-thumbnail='thumbnailUrl' md-subtitle='subtitle' md-item='items'/>
```
## Attributes

* **collection** - (required) Its value is collection of elements (users)
* **ng-model** - (required) Array for selected items to return
* **md-title** - (required) Name of the title field in your collection
* **md-thumbnail** - (required) Name of the url-thumbnail field in your collection
* **md-subtitle** - (required) Name of the subtitle field in your collection
* **items**  - (optional) Name of the field in your collection with additional thumbnails and subtitles

## Collection structure

Your collection can be implemented in three ways:
1. Simple collection 
```javascript
$scope.yourCollectionName = [{
	thumbnailUrl: './image.jpg',
	title: 'Some Title',
	subtitle: 'test@text.com'
}]
```
2. Collection with title and array of properties
```javascript
$scope.yourCollectionName = [{
	title: 'Some Title',
	items: [{subtitle: 'test@text.com', thumbnailUrl: 'image.jpg'}]
}]
```
3. Simple collection with array of properties
```javascript
$scope.yourCollectionName = [{
	thumbnailUrl: './image.jpg',
	title: 'Some Title',
	subtitle: 'test@text.com'
	items: [{subtitle: 'test_two@text.com', thumbnailUrl: 'image_two.jpg'}]
}]
```
If you don't have thumbnailUrl in items it will be taken from main object.

Youc can name your collection and properties in any way. Don't forget to write these names to apprpriate attributes.