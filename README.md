[![Android Gems](http://www.android-gems.com/badge/saiwu-bigkoo/Android-ConvenientBanner.svg?branch=master)](http://www.android-gems.com/lib/saiwu-bigkoo/Android-ConvenientBanner)

ConvenientBanner
===========

ͨ�õĹ�����ؼ�����������ʵ�ֹ��ͷЧ����֧������ѭ�������������Զ���ҳ��ʱ��(���ҷǳ����ܣ���ָ��������ͣ��ҳ���뿪�Զ���ʼ��ҳ����Ҳ���������ڽ���onPause��ʱ�򲻽����Զ���ҳ��onResume֮������Զ���ҳ)�������ṩ���ַ�ҳ��Ч��
�Ա�����������ؼ�����඼��Ҫ��Դ����иĶ����ܼ�������ͼƬ�����߰��㼯�ɲ���������Ҫ��ͼƬ����⡣������������д�������㻶ϲ������Ҫ�Կ�Դ������޸���Ϳ���ʹ���κ���ϲ��������ͼƬ�������ϡ�

## Demo
��ģ�������е�Ч������겦����ģ����̫����ԭ��ʵ��Ч����Ч��ͼ����Ŷ����
![](https://github.com/saiwu-bigkoo/Android-ConvenientBanner/blob/master/preview/convenientbannerdemo.gif)

- [demo�����뿴������](https://github.com/saiwu-bigkoo/Android-ConvenientBanner/blob/master/app/src/main/java/com/bigkoo/convenientbannerdemo/MainActivity.java)

demo����Module��ʽ��������Ҳ����ʹ��gradle ����:
```java
   compile 'com.bigkoo:convenientbanner:2.0.5'
```


##### Config in xml

```xml
<com.bigkoo.convenientbanner.ConvenientBanner
        xmlns:app="http://schemas.android.com/apk/res-auto"
        android:id="@+id/convenientBanner"
        android:layout_width="match_parent"
        android:layout_height="200dp"
        app:canLoop="true" //����ѭ�����
/>
```

### config in java code

```java
//�Զ������Holder��ʵ�ָ��ิ�ӵĽ��棬��һ����ͼƬ��ҳ�������κοؼ���ҳ��ɡ�
convenientBanner.setPages(
                new CBViewHolderCreator<LocalImageHolderView>() {
                    @Override
                    public LocalImageHolderView createHolder() {
                        return new LocalImageHolderView();
                    }
                }, localImages)
                //����������ͼƬ��Ϊ��ҳָʾ������������û��ָʾ�������Ը����Լ�������������Լ���ָʾ��,����ҪԲ��ָʾ�����ò���
                .setPageIndicator(new int[]{R.drawable.ic_page_indicator, R.drawable.ic_page_indicator_focused})
                //����ָʾ���ķ���
                .setPageIndicatorAlign(ConvenientBanner.PageIndicatorAlign.ALIGN_PARENT_RIGHT)
                //���÷�ҳ��Ч��������Ҫ��ҳЧ�����ò���
                //.setPageTransformer(Transformer.DefaultTransformer);    ������Ч֮����а��������°��Ѿ����룬���Ҫ������Ч�����ӿ��Կ�Demo�ĵ����Ӧ��
//        convenientBanner.setManualPageable(false);//���ò����ֶ�Ӱ��

public class LocalImageHolderView implements Holder<Integer>{
    private ImageView imageView;
    @Override
    public View createView(Context context) {
        imageView = new ImageView(context);
        imageView.setScaleType(ImageView.ScaleType.FIT_XY);
        return imageView;
    }

    @Override
    public void UpdateUI(Context context, final int position, Integer data) {
        imageView.setImageResource(data);
    }
}
```

## Thanks

- [ViewPagerTransforms](https://github.com/ToxicBakery/ViewPagerTransforms)
- [salvage](https://github.com/JakeWharton/salvage)
- [LoopingViewPager](https://github.com/imbryk/LoopingViewPager)

>## ����˵��
>v1.1.0 �޸�����ǰ�������һҳ���հ�ҳ��BUG  <br />
>v1.1.1 �޸�������ͼ������setTag�����BUG  <br />

>v1.1.2
 - �޸�����ˢ���Զ���ҳż��ʧЧֹͣBUG  <br />
 - �ṩonPageChangeListener��API����  <br />
 
>v1.1.3
 - ѭ�����ƣ���������Ϊ��ѭ��ģʽ  <br />
 - ����OnItemClcikListener���������޸�ԭ�ȵ��ͼƬpositionʧ׼BUG  <br />
 - ����notifyDataSetChanged������������notifyDataSetAdd����  <br />

>v1.1.4
 - getCurrentPageIndex������ΪgetCurrentItem  <br />
 - ����setcurrentitem����  <br />

>v2.0.0
 - �����޸�ѭ���߼�  <br />
 - ������ٺͰ�������  <br />
 - Demo�м�������ˢ�ºͿؼ����Ҳ�����ͻ����  <br />
 
>v2.0.1
 - �ع���1.1.4��ѭ���߼�  <br />
 - ������Ч����  <br />

>v2.0.2
 - ����setOnItemClickListener  <br />
 - �������New �ؼ��� add ListView��HeaderViewЧ������  <br />
 
>v2.0.3
 - �߼���  301230 ��Ϊ 012301230123��������һ��0��ʱ���Ϊ�ڶ���0�����һ��3��ʱ���Ϊ�ڶ���3 <br />
 
>v2.0.4
 - �޸���Ӷ���Ч��������Ч���� <br />

>v2.0.5
 - ʹ��WeakReference fix �ڴ�й©���� <br />
