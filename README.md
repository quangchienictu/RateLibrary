<pre>
RateAppDiaLog rateAppDiaLog = new RateAppDiaLog.Builder(this)
                    .setTextTitle("Your Opinion Matter To Us!")
                    .setTextContent("If you enjoy this Office Reader, would you mind rating us on the Google Play, then?")
                    .setTextButton("Rate us","Not now")
                    .setTextTitleColorLiner("#F47500","#FFBC3A")
                    .setDrawableButtonRate(R.drawable.border_rate)
                    .setColorRatingBar("#EC5656")
                    .setNumberRateInApp(5)
                    .setFontFamily(ResourcesCompat.getFont(this, R.font.xxx))
                    .setOnclickBtn(new IClickBtn() {
                        @Override
                        public void onclickNotNow() {
                            Toast.makeText(MainActivity.this,"onclickNotNow",Toast.LENGTH_SHORT).show();
                        }

                        @Override
                        public void onClickRate(float rate) {
                            Toast.makeText(MainActivity.this,rate+"",Toast.LENGTH_SHORT).show();
                        }

                        @Override
                        public void onReviewAppSuccess() {
                            finishAffinity();
                        }
                    })
                   .build();

            rateAppDiaLog.show();
</pre>





dependencies {
	        implementation 'com.github.quangchienictu:RateLibrary:1.0.0'
	}



==  R.drawable.border_rate  =====
<pre>
<code>
<shape xmlns:android="http://schemas.android.com/apk/res/android">
    <gradient android:startColor="#EC5656" android:endColor="@color/purple_700"/>
    <corners android:radius="20sp"/>
</shape>
</code>
</pre>
