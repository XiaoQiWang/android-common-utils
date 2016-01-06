# android-common-utils
this is a common utils of android (used to fast develop). contains QuickAdapter of ListView,RecyclerView.ExpandListView. and so on.

## sample code 
``` java
   mRecyclerView_room.setAdapter(mRoomAdapter = new QuickRecycleViewAdapter<RoomItem>(
                        R.layout.item_ktv_detail_room, dateItems) {
                    @Override
                    protected void onBindData(Context ctx, final int position, final RoomItem roomItem, ViewHelper helper) {
                        if (roomItem.isSelected()) {
                            helper.setBackgroundRes(R.id.fl_room, mRoomSelectDrawableId)
                                    .setTextColor(R.id.tv_room_title, mRoomSelectedColor)
                                    .setVisibility(R.id.iv_room_subscript, true);
                        } else {
                            helper.setBackgroundRes(R.id.fl_room, 0)
                                    .setTextColor(R.id.tv_room_title, mRoomUnselectColor)
                                    .setVisibility(R.id.iv_room_subscript, false);
                        }
                        helper.setText(R.id.tv_room_title, roomItem.text)
                                .setOnClickListener(R.id.fl_room, new View.OnClickListener() {
                                    public void onClick(View v) {
                                        if (getSelectedPosition() != position) {
                                            setRoomFragment(roomItem.roomInfos);
                                        }
                                        setSelected(position);
                                    }
                                });
                    }
                }
        );
```

## How to use ? 
``` java
dependencies {
     compile 'org.heaven7.core:commonutil:1.7.2'
}
```


## License

    Copyright 2015   
                    heaven7(donshine723@gmail.com)

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
