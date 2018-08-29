# 简介
读取手机图片的Exif信息，Exif是：可交换图像文件格式（英语：Exchangeable image file format，官方简称Exif），是专门为数码相机的照片设定的，可以记录数码照片的属性信息和拍摄数据
# 原理
* 主要使用了`compile 'com.drewnoakes:metadata-extractor:2.11.0'`这个包读取了图片的exif信息
# 主要代码
在MainActivity里边的
```
                final String pathGallery = FileSaveUtil.getPath(getApplicationContext(), uri);
                Log.d("ttt",pathGallery);
                final ImgInfoBean imgInfoBean = new SampleUsage().parseImgInfo(pathGallery);
                if(!TextUtils.isEmpty(imgInfoBean.getLatitude())){
//                    new Thread(new Runnable() {
//                        @Override
//                        public void run() {
                            request(imgInfoBean.getLongitude(),imgInfoBean.getLatitude());
//                        }
//                    });

                }
```
# 效果图
> 因为有些图片没有开定位拍照，或者其他原因位置信息识别出来是null
![5fcabb4330032d50ae9e83c8a7a9d0db](https://user-images.githubusercontent.com/18278015/44771730-791e2000-ab9e-11e8-8452-b089198e0401.jpg)

