<pre>
RateAppDiaLog rateAppDiaLog = new RateAppDiaLog.Builder(this)
                .setTextTitle("Your Opinion Matter To Us!")
                .setTextContent("If you enjoy this Office Reader, would you mind rating us on the Google Play, then?")
                .setTextButton("Rate us","Not now")
                .setTextTitleColor(Color.parseColor("#FFFFFF"))
                .setDrawableButtonRate(R.drawable.border_quit_exit)
                .setColorRatingBar("#FFF732")
                .setNumberRateInApp(4)
                .setTextContentColor(Color.parseColor("#FFFFFF"))
                .setTextRateUsColor(Color.parseColor("#323232"))
                .setTextNotNowColor(Color.parseColor("#FFFFFF"))
                .setOnclickBtn(new IClickBtn() {
                    @Override
                    public void onclickNotNow() {
                        finishAffinity();
                    }

                    @Override
                    public void onClickRate(float rate) {
                        if (rate < 4){
                            SharePrefUtils.forceRated(MainActivity.this);

                            String uriText = "mailto:anhnt.vtd@gmail.com?subject=FeedbackBeatMaker &body=Rate :" + rate;

                            Uri uri = Uri.parse(uriText);

                            Intent sendIntent = new Intent(Intent.ACTION_SENDTO);
                            sendIntent.setData(uri);
                            startActivity(Intent.createChooser(sendIntent, "Send Email"));
                            finishAffinity();
                        }else {
                            SharePrefUtils.forceRated(MainActivity.this);
                        }
                    }

                    @Override
                    public void onReviewAppSuccess() {
                        finishAffinity();
                    }
                }).build();
        rateAppDiaLog.show();





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
