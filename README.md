#react-native-localcache

> 本地缓存插件,可以在ios端进行查看容量,及清空缓存.

## install
npm install --save react-native-localcache


[![NPM](https://nodei.co/npm/react-native-localcache.png)](https://nodei.co/npm/react-native-localcache/)

## code
```
import Localcache from 'react-native-localcache';
export default class extends Component {
    constructor() {
        super();
        this.state = {};
    }
    componentDidMount() {
        this.getData();
    }
    async getData() {
            const _all = await Localcache.getSize();
            this.setState({
                all: Math.ceil(_all / 1024 / 1024 * 100) / 100
            });
        }
    render(){
        return(
            <View style={styles.list}>
                <Text style={styles.title}>{this.state.all}</Text>
            </View>
        )
    }

}
const styles = StyleSheet.create({
list: {
backgroundColor: '#fff', marginBottom: 10
},
title: {color: '#666', padding: 10}
});
```

## API
```
import Localcache from 'react-native-localcache';
```
### Localcache.getSize()
获取所有缓存
### Localcache.clear()
清除所有缓存
### Localcache.clearHttpCache()
清除http缓存
### Localcache.getHttpCacheSize()
获取http缓存
### Localcache.clearImageCache()
清除图片缓存
### Localcache.getImageCacheSize()
获取图片缓存

## version
- v0.0.1 update
- v0.0.4 update don't RCT defined