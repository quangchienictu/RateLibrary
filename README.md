<pre>
RateAppDiaLog rateAppDiaLog = new RateAppDiaLog.Builder(this)
                   .setTextTitle("Your Opinion Matter To Us!")
                    .setTextTitleColorLiner("#F47500","#FFBC3A")
                    .setDrawableButtonRate(R.drawable.border_rate)
                    .setExitApp(false)
                    .setColorRatingBar("#EC5656")
                    .setNumberRateInApp(5)
                    .setOnclickBtn(new IClickBtn() {
                        @Override
                        public void onclickNotNow() {
                            Toast.makeText(MainActivity.this,"ádhiasjdiasjd",Toast.LENGTH_SHORT).show();
                        }

                        @Override
                        public void onClickRate(float rate) {
                            Toast.makeText(MainActivity.this,rate+"",Toast.LENGTH_SHORT).show();
                        }
                    })
                   .build();

            rateAppDiaLog.show();
</pre>
