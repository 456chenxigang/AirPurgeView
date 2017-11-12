# AirPurgeView

## Ч��ͼ����
![main.png](http://upload-images.jianshu.io/upload_images/2646598-8db45c84c4021f47.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![mode.gif](http://upload-images.jianshu.io/upload_images/2646598-3eaf1f0b4e27eb72.gif?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## ����

``` java

Maven

<dependency>
  <groupId>com.wx.library</groupId>
  <artifactId>airpurgeview</artifactId>
  <version>1.0</version>
  <type>pom</type>
</dependency>

Gradle

compile 'com.wx.library:airpurgeview:1.0'

```

## �����õĲ���
``` java

<declare-styleable name="AirPurgeLayoutView">
	<attr name="granule_num" format="integer"/>    <!--��������-->
	<attr name="granule_radius" format="float"/>   <!--��������-->
	<attr name="granule_color" format="color"/>    <!--������ɫ,��ò�͸����-->

	<attr name="circle_proportion" format="float"/>  <!--Բ��ֱ����Сռ�������С���Ǹ��ı���-->
	<attr name="main_color" format="color"/>            <!--ʵ��Բ������ҶԲ�����������ɫ-->
	<attr name="solidring_width" format="float"/>    <!--����Ȧʵ��Բ���Ŀ�ȣ���ò�Ҫ̫��-->
	<attr name="dashedring_width" format="float"/>    <!--��ҶԲ���Ŀ�ȣ���������solidwidth�ı���ã������ʵ�����-->
	<attr name="toptitle" format="string"/>
	<attr name="centertitle" format="string"/>
	<attr name="bottomtitle" format="string"/>
	<attr name="toptitle_textsize" format="dimension"/>
	<attr name="centertitle_textsize" format="dimension"/>
	<attr name="bottomtitle_textsize" format="dimension"/>
	<attr name="speed_level" format="integer"/>     <!--����Ĭ��3000�������޸�-->
	<attr name="eachpan_angle" format="float"/>    <!--ÿƬ��Ҷ�ĽǶ� �Լ�Ҫ����üӼ�϶ һ��360-->
	<attr name="eachpan_anglegap" format="float"/>    <!--������Ҷ�ļ�϶-->
</declare-styleable>

```

## sample

> XML

``` java

<com.wx.airpurgeview.AirPurgeLayoutView
        android:id="@+id/airpurge_view"
        android:layout_width="match_parent"
        android:layout_height="400dp"
        app:toptitle="PM2.5"
        app:centertitle="521"
        app:bottomtitle="������"/>

```

> Java

``` java

btnChangeNum.setOnClickListener {
            clearMode1Anim()
            mAirPurgeView.setCenterTitle(random.nextInt(600).toString())
        }
        btnChangeBg.setOnClickListener {
            clearMode1Anim()
            if (colorIndex >= bgColors.size) colorIndex = 0
            mAirPurgeView.setBackgroundColor(bgColors[colorIndex],1000)
            colorIndex += 1
        }
        btnChangeStart.setOnClickListener {
            clearMode1Anim()
            mAirPurgeView.onOpenAirPurge()
        }
        btnChangeEnd.setOnClickListener {
            clearMode1Anim()
            mAirPurgeView.onCloseAirPurge()
        }
        btnChangeSpeed.setOnClickListener {
            clearMode1Anim()
            if (colorIndex >= bgColors.size || colorIndex <= 0) colorIndex = bgColors.size - 1
            mAirPurgeView.setSpeedLevel(colorIndex*1000.toLong())
            colorIndex -= 1
        }
        btnOpenGranlue.setOnClickListener {
            clearMode1Anim()
            mAirPurgeView.onOpenGranule(false)
        }
        btnCloseGranlue.setOnClickListener {
            clearMode1Anim()
            mAirPurgeView.onClearAllGranule()
        }
        btnChangeGranuleMode.setOnClickListener {
            clearMode1Anim()
            mAirPurgeView.onChangeGranuleMode(!mAirPurgeView.getGranuleMode())
        }


```

## �������������������ʱ��͸Ľ�������

## ����ʹ�ù����������⣬Ҳ����и��¡�����