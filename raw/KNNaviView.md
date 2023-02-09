# Kakao Navi SDK with UI


> KNNaviView
- NaviView에 관해서 작성합니다.
---

>initWithGuidance

```kotlin
public final fun initWithGuidance(aGuidance: com.kakaomobility.knsdk.guidance.knguidance.KNGuidance, aTrip: com.kakaomobility.knsdk.trip.kntrip.KNTrip?, aRoutePriority: com.kakaomobility.knsdk.KNRoutePriority, aAvoidOptions: kotlin.Int): kotlin.Unit
```

```kotlin
_naviView.initWithGuidance(_guidance, _trip, KNRoutePriority.KNRoutePriority_Recommand, KNRouteAvoidOption.KNRouteAvoidOption_None.value)
```

- initWithGuidance는 guidance를 생성합니다.
- guidance를 사용하기 위해서는 initWithGuidance를 선언해주서야 합니다.
- init된 guidance는 _guidance에 들어갑니다.
- _trip이 **null**일 경우, 안전운행 모드로 실행됩니다.
- initWithGuidance와 _guidance.startWithTrip을 같이 사용하면 가이드 안내음이 두번 출력됩니다.
---


>changeDisplayType

```kotlin
public final fun changeDisplayType(displayType: com.kakaomobility.knsdk.KNDisplayType): kotlin.Unit
```

```kotlin
_naviView.changeDisplayType(KNDisplayType.KNDisplayType_DRIVE)
_naviView.changeDisplayType(KNDisplayType.KNDisplayType_SEARCH)
```

- 지도의 이미지(색상)에 변경이 있어보입니다.
- KNDisplayType.KNDisplayType_DRIVE
![이미지?](https://drive.google.com/uc?export=download&id=1HYi7IdicKIeNyjMZFDeRSeM51KOhbSZQ)s
- KNDisplayType.KNDisplayType_SEARCH
![](/images/2023-02-06-18-06-53.png)
---


>mapViewWillMoveToMap

```kotlin
public open fun mapViewWillMoveToMap(): kotlin.Unit
```

```kotlin
_naviView.mapViewWillMoveToMap()
```

- 가이드 중 화면을 움직였을때 모습을 보여줍니다.(경로안내/안전운행)
![](Images/2023-02-06-18-12-55.png)
![](Images/2023-02-06-18-13-05.png)
---


>mapViewDidSingleTap

```kotlin
public open fun mapViewDidSingleTap(): kotlin.Unit
```

```kotlin
_naviView.mapViewDidSingleTap()
```

- 화면을 한번 터치했을때 모습을 보여줍니다.
- 가이드 중 에만 동작하며 하단 메뉴바 터치와 같은 기능을 합니다.(경로안내)
![](Images/2023-02-06-18-26-23.png)
---


>mapViewDidDoubleTap

```kotlin
public open fun mapViewDidDoubleTap(): kotlin.Unit
```

```kotlin
_naviView.mapViewDidDoubleTap()
```

- 화면을 빠르게 두번 터치했을때 모습을 보여줍니다.
- 가이드 중 에만 동작하며 '전체 경로보기' 기능을 합니다.(경로안내)
![](Images/2023-02-06-18-28-05.png)
---


>mapViewPanningStarted

```kotlin
public open fun mapViewPanningStarted(): kotlin.Unit
```

```kotlin
_naviView.mapViewPanningStarted()
```

- //TODO 기능확인 필요
---


>mapViewZoomingStarted

```kotlin
public open fun mapViewZoomingStarted(): kotlin.Unit
```

```kotlin
_naviView.mapViewZoomingStarted()
```

- //TODO 기능확인 필요
---


>mapViewChangeRoute

```kotlin
public open fun mapViewChangeRoute(aRoute: com.kakaomobility.knsdk.trip.kntrip.knroute.KNRoute?): kotlin.Unit
```

```kotlin
_naviView.mapViewChangeRoute(_route)
```

- 설정된 _route로 경로를 표기해줍니다.
- 경로가 표기되기 위해서는 가이드에 대안경로가 있어야 됩니다. 대안경로가 없다면 동작하지 않습니다.
- 대안경로가 있다는 가정하에 호출하면 대안경로와 기존경로를 번갈아가며 노출합니다.
![](Images/2023-02-07-10-56-02.png)
![](Images/2023-02-07-10-56-10.png)
---


>mapViewViaPointTouched

```kotlin
public open fun mapViewViaPointTouched(aPoi: com.kakaomobility.knsdk.common.objects.KNPOI): kotlin.Unit
```

```kotlin
_naviView.mapViewViaPointTouched(_goal!!)
```

- 특정 POI에 대한 패널이 노출이 됩니다.
- 다만 해당기능이 다른 작업을 하는 것은 확인하지 못했습니다.
![](Images/2023-02-07-10-58-42.png)
---


>mapViewYugoPointTouched

```kotlin
public open fun mapViewYugoPointTouched(aRoadEvent: com.kakaomobility.knsdk.guidance.knguidance.routeguide.objects.KNRoadEvent): kotlin.Unit
```

```kotlin

```

- //TODO 기능확인필요. 아마 도로사고 및 공사 관련 정보를 넣을 수 있을 것 같습니다.
---


>mapViewAroundPoiTouched

```kotlin
public open fun mapViewAroundPoiTouched(aCoord: com.kakaomobility.knsdk.common.util.IntPoint, aPoiAroundDataList: kotlin.collections.List<com.kakaomobility.knsdk.api.objects.KNPoiAroundData>, aCode: com.kakaomobility.knsdk.ui.manager.KNCategoryPoiCode): kotlin.Unit
```

```kotlin

```

- //TODO 기능확인필요. 아마 특정 지점 인근의 정보 목록을 노출 할 것 같습니다.
---


>mapAroundPinListViewAroundPoiTouched

```kotlin
public open fun mapAroundPinListViewAroundPoiTouched(aPoiAroundData: com.kakaomobility.knsdk.api.objects.KNPoiAroundData, aCode: com.kakaomobility.knsdk.ui.manager.KNCategoryPoiCode): kotlin.Unit
```

```kotlin

```

- //TODO 기능확인필요. 아마 특정 지점 인근의 정보 목록을 노출 할 것 같습니다.
---


>highwayModeBgViewReqChangeViewMode

```kotlin
public open fun highwayModeBgViewReqChangeViewMode(aViewState: com.kakaomobility.knsdk.ui.view.KNNaviViewState): kotlin.Unit
```

```kotlin
_naviView.highwayModeBgViewReqChangeViewMode(KNNaviViewState.NONE)
_naviView.highwayModeBgViewReqChangeViewMode(KNNaviViewState.DriveNormal)
_naviView.highwayModeBgViewReqChangeViewMode(KNNaviViewState.DriveTouch)
_naviView.highwayModeBgViewReqChangeViewMode(KNNaviViewState.DriveFullRoute)
_naviView.highwayModeBgViewReqChangeViewMode(KNNaviViewState.DriveSection)
_naviView.highwayModeBgViewReqChangeViewMode(KNNaviViewState.DriveHighwayMode)
_naviView.highwayModeBgViewReqChangeViewMode(KNNaviViewState.SafetyNormal)
_naviView.highwayModeBgViewReqChangeViewMode(KNNaviViewState.SafetyTouch)
```

- MapView의 배경을 KNNaviViewState에 따라 새로 그려줍니다. 루트경로는 새로 그려주지 않습니다.
- KNNaviViewState.NONE (표기없음)
![](Images/2023-02-07-12-13-23.png)
![](Images/2023-02-07-12-13-34.png)
- KNNaviViewState.DriveNormal (경로주행)
![](Images/2023-02-07-12-15-03.png)
![](Images/2023-02-07-12-15-10.png)
- KNNaviViewState.DriveTouch (경로주행 중 터치)
![](Images/2023-02-07-13-48-25.png)
![](Images/2023-02-07-13-48-33.png)
- KNNaviViewState.DriveFullRoute (전체경로)
![](Images/2023-02-07-13-49-07.png)
- KNNaviViewState.DriveSection (경로목록)
![](Images/2023-02-07-14-17-02.png)
- KNNaviViewState.DriveHighwayMode (고속도로주행?)
![](Images/2023-02-07-14-18-03.png)
- KNNaviViewState.SafetyNormal (안전운행)
![](Images/2023-02-07-14-18-40.png)
- KNNaviViewState.SafetyTouch (안전운행 중 터치)
![](Images/2023-02-07-14-18-53.png)
---


>KNComponentRouteInfoViewChangedRoute

```kotlin
public open fun KNComponentRouteInfoViewChangedRoute(aChanged: kotlin.Boolean): kotlin.Unit
```

```kotlin
_naviView.KNComponentRouteInfoViewChangedRoute(false)
_naviView.KNComponentRouteInfoViewChangedRoute(true)
```

- 대안 경로가 있을때만 동작. 없으면 Error. false면 기존경로 true면 대안경로를 선택합니다.
- 경로표기와 상단 안내는 바꾸어주지만 실제 가이드 안내 내용변화는 없습니다.
![](Images/2023-02-07-15-32-06.png)
![](Images/2023-02-07-15-32-12.png)
---


>KNComponentRouteInfoViewRouteSelect

```kotlin
public open fun KNComponentRouteInfoViewRouteSelect(routeList: kotlin.collections.List<com.kakaomobility.knsdk.trip.kntrip.knroute.KNRoute>, fixScale: kotlin.Boolean): kotlin.Unit
```

```kotlin
_naviView.KNComponentRouteInfoViewRouteSelect(_routeList!!, true)
```

- **NaviView.initWithGuidance** 설정된 경로와 **Trip.routeWithPriority** 로 설정된 경로가 다르다는 걸 보여주는 항목입니다.
- KNComponentRouteInfoViewRouteSelect는 Trip.routeWithPriority으로 생성된 routeList 사용합니다.
- Boolean값이 **true**면 축소된 화면에서, **false**면 경로 전체가 표현된 화면에서 경로를 보여줍니다.
![](Images/2023-02-07-15-53-52.png)
---


>KNComponentRouteInfoViewRefresh

```kotlin
public open fun KNComponentRouteInfoViewRefresh(): kotlin.Unit
```

```kotlin
_naviView.KNComponentRouteInfoViewRefresh()
```

- 경로 새로고쳐서 보여줍니다. 사용자의 위치를 기기 가운데로 강제로 설정하는 것 같습니다.
---


>KNComponentRouteInfoViewShowSectionInfo

```kotlin
public open fun KNComponentRouteInfoViewShowSectionInfo(routeList: kotlin.collections.List<com.kakaomobility.knsdk.trip.kntrip.knroute.KNRoute>): kotlin.Unit
```

```kotlin
_naviView.KNComponentRouteInfoViewShowSectionInfo(_routeList!!)
```

- 경로(route)의 상세 목차를 보여줍니다.
![](Images/2023-02-07-15-54-06.png)
---


>KNComponentRouteInfoViewTrafficMode

```kotlin
public open fun KNComponentRouteInfoViewTrafficMode(routeList: kotlin.collections.List<com.kakaomobility.knsdk.trip.kntrip.knroute.KNRoute>?): kotlin.Unit
```

```kotlin
_naviView.KNComponentRouteInfoViewTrafficMode(_routeList!!)
```

- //TODO 바뀐점 모르겠음
---


>KNComponentRouteInfoViewClosePopup

```kotlin
public open fun KNComponentRouteInfoViewClosePopup(): kotlin.Unit
```

```kotlin
_naviView.KNComponentRouteInfoViewClosePopup()
```

- //TODO 바뀐점 모르겠음
---


>KNComponentSectionInfoViewSectionSelect

```kotlin
public open fun KNComponentSectionInfoViewSectionSelect(aPoint: com.kakaomobility.knsdk.common.util.FloatPoint): kotlin.Unit
```

```kotlin
_naviView.KNComponentSectionInfoViewSectionSelect(FloatPoint(_start!!.pos.x.toFloat(),_start!!.pos.y.toFloat()))
```

- 하단 전체경로를 통해서 전체 경로를 확인해야 제대로 작동하는 것을 확인.
- 전체경로에서 특정지점을 중심으로 경로를 표시해줍니다.
---


>KNComponentSectionInfoViewRouteSelect

```kotlin
public open fun KNComponentSectionInfoViewRouteSelect(aRoute: com.kakaomobility.knsdk.trip.kntrip.knroute.KNRoute): kotlin.Unit
```

```kotlin
_naviView.KNComponentSectionInfoViewRouteSelect(_route!!)
```

- 하단 전체경로를 통해서 전체 경로를 확인해야 제대로 작동하는 것을 확인.
- 전체경로에서 선택한 경로를 표시해줍니다.
---


>KNComponentSectionInfoViewClose

```kotlin
public open fun KNComponentSectionInfoViewClose(): kotlin.Unit
```

```kotlin
_naviView.KNComponentSectionInfoViewClose()
```

- 하단 전체경로를 통해서 전체 경로를 확인해야 제대로 작동하는 것을 확인.
- 가이드를 닫고 전체경로를 보여줍니다.
---


>KNComponentSectionInfoViewRefresh

```kotlin
public open fun KNComponentSectionInfoViewRefresh(): kotlin.Unit
```

```kotlin
_naviView.KNComponentSectionInfoViewRefresh()
```

- 하단 전체경로를 통해서 전체 경로를 확인해야 제대로 작동하는 것을 확인.
- //TODO : 새로고침인것 같은데 잘모르겠음
---


>highwayModeViewReqChangeViewMode

```kotlin
public open fun highwayModeViewReqChangeViewMode(aViewState: com.kakaomobility.knsdk.ui.view.KNNaviViewState): kotlin.Unit
```

```kotlin
_naviView.highwayModeViewReqChangeViewMode(KNNaviViewState.NONE)
```

- highwayModeBgViewReqChangeViewMode와 차이점을 모르겠습니다.
---


>zoomViewWillZoomIn

```kotlin
public open fun zoomViewWillZoomIn(): kotlin.Unit
```

```kotlin
_naviView.zoomViewWillZoomIn()
```

- NaviView 줌인 기능입니다. 클릭상태가 아니라면 금방 상태가 풀립니다. (mapViewWillMoveToMap 과 같이 사용해야 할 듯)
---


>zoomViewWillZoomOut

```kotlin
public open fun zoomViewWillZoomOut(): kotlin.Unit
```

```kotlin
_naviView.zoomViewWillZoomOut()
```

- NaviView 줌아웃 기능입니다. 클릭상태가 아니라면 금방 상태가 풀립니다. (mapViewWillMoveToMap 과 같이 사용해야 할 듯)
---


>popupInfoViewWillRemoveVia

```kotlin
public open fun popupInfoViewWillAddVia(aVia: kotlin.Any, popupStyle: kotlin.Int): kotlin.Unit
```

```kotlin
_naviView.popupInfoViewWillRemoveVia(_start!!)
```

- 특정 POI를 지우고 표현하는 것같은데 잘모르겠음. 바로 가이드 화면으로 표현해줌.
---


>popupInfoViewWillAddVia

```kotlin
public open fun popupInfoViewWillAddVia(aVia: kotlin.Any, popupStyle: kotlin.Int): kotlin.Unit
```

```kotlin
_naviView.popupInfoViewWillAddVia(_start!!,1)
```

- 특정 POI를 추가하고 표현하는 것같은데 잘모르겠음.
---


>popupInfoViewWillGoToGoal

```kotlin
public open fun popupInfoViewWillGoToGoal(aGoal: com.kakaomobility.knsdk.common.objects.KNPOI): kotlin.Unit
```

```kotlin
_naviView.popupInfoViewWillGoToGoal(_goal!!)
```

- 목적지 정보만 주면 바로 길안내 가능.
---


>popupInfoViewClose

```kotlin
public open fun popupInfoViewClose(view: android.view.View): kotlin.Unit
```

```kotlin
_naviView.popupInfoViewClose(view)
```

- 팝업뷰를 닫는것 같은데 잘모르겠음.
---


>aroundMenuViewClickMenuBtn

```kotlin
public open fun aroundMenuViewClickMenuBtn(): kotlin.Unit
```

```kotlin
_naviView.aroundMenuViewClickMenuBtn()
```

- //TODO 뭔지 모르겠음
---


>aroundMenuViewSelectItem

```kotlin
public open fun aroundMenuViewSelectItem(aMenuData: com.kakaomobility.knsdk.n1.a): kotlin.Unit
```

```kotlin
_naviView.aroundMenuViewSelectItem()
```

- //TODO 뭔지 모르겠음
---


>bottomViewGuideEnded

```kotlin
public open fun bottomViewGuideEnded(): kotlin.Unit
```

```kotlin
_naviView.bottomViewGuideEnded()
```

- 가이드 중 하단 메뉴의 "길안내 종료" 기능
---


>bottomViewGuideReroute

```kotlin
public open fun bottomViewGuideReroute(): kotlin.Unit
```

```kotlin
_naviView.bottomViewGuideReroute()
```

- 가이드 중 하단 메뉴의 "새로고침" 기능
---


>bottomViewOnMenu

```kotlin
public open fun bottomViewOnMenu(): kotlin.Unit
```

```kotlin
_naviView.bottomViewOnMenu()
```

- 가이드 중 하단 메뉴의 "메뉴클릭" 기능
![](Images/2023-02-08-11-09-36.png)
---


>bottomMenuViewFullRoute

```kotlin
public open fun bottomMenuViewFullRoute(): kotlin.Unit
```

```kotlin
_naviView.bottomMenuViewFullRoute()
```

- 가이드 중 하단 메뉴의 "전체경로" 기능
![](Images/2023-02-08-11-11-17.png)
---


>bottomMenuViewAnotherRoute

```kotlin
public open fun bottomMenuViewAnotherRoute(): kotlin.Unit
```

```kotlin
_naviView.bottomMenuViewAnotherRoute()
```

- 가이드 중 하단 메뉴의 "다른경로" 기능
![](Images/2023-02-08-11-13-34.png)
---


>bottomMenuViewCancelRoute

```kotlin
public open fun bottomMenuViewCancelRoute(): kotlin.Unit
```

```kotlin
_naviView.bottomMenuViewCancelRoute()
```

- 가이드 중 하단 메뉴의 "경로취소" 기능
- **NaviView.bottomMenuComponent.useGuideCancel = false**와 관계없이 동작
---


>bottomMenuViewCancelRoute

```kotlin
public open fun bottomMenuViewCancelRoute(): kotlin.Unit
```

```kotlin
_naviView.bottomMenuViewCancelRoute()
```

- 가이드 중 하단 메뉴의 "경로취소" 기능
---


>bottomMenuViewRemoveVia

```kotlin
public open fun bottomMenuViewRemoveVia(): kotlin.Unit
```

```kotlin
_naviView.bottomMenuViewRemoveVia()
```

- 가이드 중 "경유지삭제" 기능. 앞선 순위의 경유지부터 삭제한다.
---


>bottomMenuViewDriveSetting

```kotlin
public open fun bottomMenuViewDriveSetting(): kotlin.Unit
```

```kotlin
_naviView.bottomMenuViewDriveSetting()
```

- 가이드 중 하단 메뉴의 "주행설정" 기능
![](Images/2023-02-08-11-28-32.png)
---


>bottomMenuViewGuideEnded

```kotlin
public open fun bottomMenuViewGuideEnded(): kotlin.Unit
```

```kotlin
_naviView.bottomMenuViewGuideEnded()
```

- 가이드 중 하단 메뉴의 "길안내 종료" 기능
---


>curPositionViewToCurLocation

```kotlin
public open fun curPositionViewToCurLocation(): kotlin.Unit
```

```kotlin
_naviView.curPositionViewToCurLocation()
```

- 가이드 중 하단 메뉴의 "현위치로" 기능
---


> emergencyButtonViewClick

```kotlin
public open fun emergencyButtonViewClick(): kotlin.Unit { /* compiled code */ }
```

```kotlin
_naviView.emergencyButtonViewClick()
```

- //TODO: 확인필요
---


>accidentButtonViewClick

```kotlin
public open fun accidentButtonViewClick(): kotlin.Unit { /* compiled code */ }
```

```kotlin
_naviView.accidentButtonViewClick()
```

- //TODO: 확인필요
---


##guideStateDelegate 관련 function
상기 function들은 guideState를 받기 위한 함수들입니다. Override되어있으며 데이터가 들어올때 해당 정보를 처리해줍니다.(Reciever)
guideStateDelegate는 주행중 안내 상태가 변경될 때 호출됩니다.
- guidanceGuideStarted
- guidanceCheckingRouteChange
- guidanceRouteUnchanged
- guidanceRouteUnchangedWithError
- guidanceOutOfRoute
- guidanceRouteChanged
- guidanceGuideEnded
- guidanceDidUpdateRoutes
  
>guidanceGuideStarted

```kotlin
public final fun guidanceGuideStarted(aGuidance: com.kakaomobility.knsdk.guidance.knguidance.KNGuidance): kotlin.Unit
```

```kotlin
override fun guidanceGuideStarted(aGuidance: KNGuidance) {
    _naviView.guidanceGuideStarted(aGuidance)
}
```

- 길안내 시작시 호출. "안내를 시작" 음성 안내가 발생하는 시점
---


>guidanceCheckingRouteChange

```kotlin
public final fun guidanceCheckingRouteChange(aGuidance: com.kakaomobility.knsdk.guidance.knguidance.KNGuidance): kotlin.Unit
```

```kotlin
override fun guidanceCheckingRouteChange(aGuidance: KNGuidance) {
    _naviView.guidanceCheckingRouteChange(aGuidance)
}
```

- 경로가 변경되면 호출. "교통변화를 감시" 음성안내가 발생하는 시점
---


>guidanceRouteUnchanged

```kotlin
public final fun guidanceRouteUnchanged(aGuidance: com.kakaomobility.knsdk.guidance.knguidance.KNGuidance): kotlin.Unit
```

```kotlin
override fun guidanceRouteUnchanged(aGuidance: KNGuidance) {
    _naviView.guidanceRouteUnchanged(aGuidance)
}
```

- 수신받은 새경로가 기존의 경로와 동일한 경우 호출. "기존경로로 안내" 음성안내가 발생하는 시점
---


>guidanceRouteUnchangedWithError

```kotlin
public final fun guidanceRouteUnchangedWithError(aGuidnace: com.kakaomobility.knsdk.guidance.knguidance.KNGuidance, aError: com.kakaomobility.knsdk.common.objects.KNError): kotlin.Unit
```

```kotlin
override fun guidanceRouteUnchangedWithError(aGuidnace: KNGuidance, aError: KNError) {
    _naviView.guidanceRouteUnchangedWithError(aGuidnace, aError)
}
```

- 경로 오류시 호출. 기존경로를 이탈해도 경로 재탐색 없고 GPS신호를 따라 길안내 유지.
- 다시 경로를 탐색하려면 수동으로 경로를 탐색해야하며 현재 위치가 기존의 경로를 벗어낫을때만 새경로 안내
---


>guidanceOutOfRoute

```kotlin
public final fun guidanceOutOfRoute(aGuidance: com.kakaomobility.knsdk.guidance.knguidance.KNGuidance): kotlin.Unit
```

```kotlin
override fun guidanceOutOfRoute(aGuidance: KNGuidance) {
    _naviView.guidanceOutOfRoute(aGuidance)
}
```

- 경로에서 이탈한 뒤 새로운 경로 요청시 호출. "경로 이탈 재검색" 음성안내가 발생하는 시점
---


>guidanceRouteChanged

```kotlin
public final fun guidanceRouteChanged(aGuidance: com.kakaomobility.knsdk.guidance.knguidance.KNGuidance): kotlin.Unit
```

```kotlin
override fun guidanceRouteChanged(aGuidance: KNGuidance) {
    _naviView.guidanceRouteChanged(aGuidance)
}
```

- 수신받은 새경로가 기존의 안내된 경로와 다를경우 호출. "경로 변경, 새로운 길안내" 음성안내가 발생하는 시점
---


>guidanceGuideEnded

```kotlin
public final fun guidanceGuideEnded(aGuidance: com.kakaomobility.knsdk.guidance.knguidance.KNGuidance, isShowDriveResultDialog: kotlin.Boolean /* = compiled code */): kotlin.Unit 
```

```kotlin
override fun guidanceGuideEnded(aGuidance: KNGuidance) {
    _naviView.guidanceGuideEnded(aGuidance, false)
}
```

- 길안내가 종료되면 호출. "목적지 도착. 안내 종료" 음성안내가 발생하는 시점
- isShowDriveResultDialog가 true이면 길안내 완료 다이얼로그팝업이 노출, false면 비노출.
---


>guidanceDidUpdateRoutes

```kotlin
public final fun guidanceDidUpdateRoutes(aGuidance: com.kakaomobility.knsdk.guidance.knguidance.KNGuidance, aRoutes: kotlin.collections.List<com.kakaomobility.knsdk.trip.kntrip.knroute.KNRoute>, aMultiRouteInfo: com.kakaomobility.knsdk.guidance.knguidance.routeguide.objects.KNMultiRouteInfo?): kotlin.Unit
```

```kotlin
override fun guidanceDidUpdateRoutes(
        aGuidance: KNGuidance,
        aRoutes: List<KNRoute>,
        aMultiRouteInfo: KNMultiRouteInfo?
) {
    _naviView.guidanceDidUpdateRoutes(aGuidance, aRoutes, aMultiRouteInfo)
}
```

- 주행중 기타요인으로 경로가 변경되었을때 호출. 
- guidanceRouteUnchange/Changed와 별개로 동작하며 동일한 경로라도 경로데이터가 변경되었을 경우 호출될 수 있음
---


##locationGuideDelegate 관련 function
상기 function들은 locationGuide를 받기 위한 함수들입니다. Override되어있으며 데이터가 들어올때 해당 정보를 처리해줍니다.(Reciever)
locationGuideDelegate 위치를 나타냄. 주행중 안내 위치가 변경될 때 호출. 현재는 매번 GPS신호를 수신할 때마다 호출.
- guidanceDidUpdateLocation

>guidanceDidUpdateLocation

```kotlin
public final fun guidanceDidUpdateLocation(aGuidance: com.kakaomobility.knsdk.guidance.knguidance.KNGuidance, aLocationGuide: com.kakaomobility.knsdk.guidance.knguidance.locationguide.KNGuide_Location): kotlin.Unit
```

```kotlin
override fun guidanceDidUpdateLocation(
        aGuidance: KNGuidance,
        aLocationGuide: KNGuide_Location
) {        
    _naviView.guidanceDidUpdateLocation(aGuidance, aLocationGuide)
}
```

- 위지 정보가 변경될 경우 호출. locationGuide항목이 1개 이상 변경시 전달. 세부항목중 변경이 없는 것은 동일한 객체로 전달
---


##routeGuideDelegate 관련 function
상기 function들은 routeGuide를 받기 위한 함수들입니다. Override되어있으며 데이터가 들어올때 해당 정보를 처리해줍니다.(Reciever)
routeGuideDelegate는 경로를 안내하는 델리게이트. 주행중 경로 안내 정보가 변경될 때 호출
- guidanceDidUpdateRouteGuide

>guidanceDidUpdateRouteGuide

```kotlin
public final fun guidanceDidUpdateRouteGuide(aGuidance: com.kakaomobility.knsdk.guidance.knguidance.KNGuidance, aRouteGuide: com.kakaomobility.knsdk.guidance.knguidance.routeguide.KNGuide_Route): kotlin.Unit
```

```kotlin
override fun guidanceDidUpdateRouteGuide(aGuidance: KNGuidance, aRouteGuide: KNGuide_Route) {
    _naviView.guidanceDidUpdateRouteGuide(aGuidance, aRouteGuide)
}
```

- 경로 안내 정보를 업데이트. routeGuide의 항목 1개 이상 변경시 전달. 세부항목중 변경없는 것은 동일한 객체로 전달
---


##safetyGuideDelegate 관련 function
상기 function들은 safetyGuide를 받기 위한 함수들입니다. Override되어있으며 데이터가 들어올때 해당 정보를 처리해줍니다.(Reciever)
safetyGuideDelegate는 안전운행 델리게이트. 안전운행 정보가 변경될 때 호출.
- guidanceDidUpdateSafetyGuide
- guidanceDidUpdateAroundSafeties

>guidanceDidUpdateSafetyGuide

```kotlin
public final fun guidanceDidUpdateSafetyGuide(aGuidance: com.kakaomobility.knsdk.guidance.knguidance.KNGuidance, aSafetyGuide: com.kakaomobility.knsdk.guidance.knguidance.safetyguide.KNGuide_Safety?): kotlin.Unit
```

```kotlin
override fun guidanceDidUpdateSafetyGuide(
        aGuidance: KNGuidance,
        aSafetyGuide: KNGuide_Safety?
) {
    _naviView.guidanceDidUpdateSafetyGuide(aGuidance, aSafetyGuide)
}
```

- 안전운행 정보 업데이트. safetyGuide 항목 1개 이상 변경시 전달. 변경없는 것은 동일한 객체로 전달
---


>guidanceDidUpdateAroundSafeties

```kotlin
public final fun guidanceDidUpdateAroundSafeties(aGuidance: com.kakaomobility.knsdk.guidance.knguidance.KNGuidance, aSafeties: kotlin.collections.List<com.kakaomobility.knsdk.guidance.knguidance.safetyguide.objects.KNSafety>?): kotlin.Unit
```

```kotlin
override fun guidanceDidUpdateAroundSafeties(
        aGuidance: KNGuidance,
        aSafeties: List<KNSafety>?
) {
    _naviView.guidanceDidUpdateAroundSafeties(aGuidance, aSafeties)
}
```

- 주변 안전운행 정보 업데이트
---


##voiceGuideDelegate 관련 function
상기 function들은 voiceGuide 받기 위한 함수들입니다. Override되어있으며 데이터가 들어올때 해당 정보를 처리해줍니다.(Reciever)
voiceGuideDelegate는 음성안내 델리게이트. 음성안내 시작 및 종료와 관련된 정보 요청 및 전달.
- shouldPlayVoiceGuide
- willPlayVoiceGuide
- didFinishPlayVoiceGuide

>shouldPlayVoiceGuide

```kotlin
public final fun shouldPlayVoiceGuide(aGuidance: com.kakaomobility.knsdk.guidance.knguidance.KNGuidance, aVoiceGuide: com.kakaomobility.knsdk.guidance.knguidance.voiceguide.KNGuide_Voice, aNewData: kotlin.collections.MutableList<kotlin.ByteArray>): kotlin.Boolean
```

```kotlin
override fun shouldPlayVoiceGuide(
        aGuidance: KNGuidance,
        aVoiceGuide: KNGuide_Voice,
        aNewData: MutableList<ByteArray>
): Boolean {
    return _naviView.shouldPlayVoiceGuide(aGuidance, aVoiceGuide, aNewData)
}
```

- 음성안내 사용여부 설정
- 다음과 같은 형식으로 각 음성종류의 출력여부를 결정할 수 있다.
```kotlin
if(aVoiceGuide.voiceCode == KNVoiceCode.KNVoiceCode_StartGuide)
    return true
```
- 각 음성의 종류는 다음과 같다.
  * KNVoiceCode.KNVoiceCode_Turn : 회전구간 안내
  * KNVoiceCode.KNVoiceCode_Safety : 안전운전 안내
  * KNVoiceCode.KNVoiceCode_StartGuide : 음성안내 시작 ("안내를 시작하겠습니다.")
  * KNVoiceCode.KNVoiceCode_EndGuide : 음성안내 종료
  * KNVoiceCode.KNVoiceCode_DetailDir : 상세교차로 차선안내
  * KNVoiceCode.KNVoiceCode_MultiRoute : 다중경로 분기점안내
  * KNVoiceCode.KNVoiceCode_SchoolZone : 어린이보호구역 안내
  * KNVoiceCode.KNVoiceCode_Hipass : 하이패스 차선안내
  * KNVoiceCode.KNVoiceCode_StrateToNext : 직진안내
  * KNVoiceCode.KNVoiceCode_CheckingRouteChange : 교통변화 안내 ("교통변화를 감지중입니다.")
  * KNVoiceCode.KNVoiceCode_RouteChanged : 경로변경 안내 ("교통상황이 변하여 새로운 경로로 안내합니다.")
  * KNVoiceCode.KNVoiceCode_RouteUnchanged : 기존경로 안내 ("기존 경로로 계속 안내합니다.")
  * KNVoiceCode.KNVoiceCode_OutOfRoute : 경로 이탈 안내 ("경로를 이탈하였습니다.")
  * KNVoiceCode.KNVoiceCode_GPSConnected : GPS연결 안내
  * KNVoiceCode.KNVoiceCode_Alram : 알람(안전운전 지점 통과 등)
  * KNVoiceCode.KNVoiceCode_Alert : 경고(속도 초과 등)
  * KNVoiceCode.KNVoiceCode_LinkSound : 링크기반 음성
---


>willPlayVoiceGuide

```kotlin
public final fun willPlayVoiceGuide(aGuidance: com.kakaomobility.knsdk.guidance.knguidance.KNGuidance, aVoiceGuide: com.kakaomobility.knsdk.guidance.knguidance.voiceguide.KNGuide_Voice): kotlin.Unit
```

```kotlin
override fun willPlayVoiceGuide(aGuidance: KNGuidance, aVoiceGuide: KNGuide_Voice) {
    _naviView.willPlayVoiceGuide(aGuidance, aVoiceGuide)
}
```

- 음성 안내를 시작합니다.
---


>didFinishPlayVoiceGuide

```kotlin
public final fun didFinishPlayVoiceGuide(aGuidance: com.kakaomobility.knsdk.guidance.knguidance.KNGuidance, aVoiceGuide: com.kakaomobility.knsdk.guidance.knguidance.voiceguide.KNGuide_Voice): kotlin.Unit
```

```kotlin
override fun didFinishPlayVoiceGuide(aGuidance: KNGuidance, aVoiceGuide: KNGuide_Voice) {
    _naviView.didFinishPlayVoiceGuide(aGuidance, aVoiceGuide)
}
```

- 음성 안내를 종료합니다.
---


##citsGuideDelegate 관련 function
상기 function들은 citsGuide를 받기 위한 함수들입니다. Override되어있으며 데이터가 들어올때 해당 정보를 처리해줍니다.(Reciever)
citsGuideDelegate는 C-ITS(협력지능형교통체계) 정보가 변경되면 호출
- didUpdateCitsGuide

> didUpdateCitsGuide

```kotlin
public final fun didUpdateCitsGuide(aGuidance: com.kakaomobility.knsdk.guidance.knguidance.KNGuidance, aCitsGuide: com.kakaomobility.knsdk.guidance.knguidance.citsguide.KNGuide_Cits): kotlin.Unit
```

```kotlin
override fun didUpdateCitsGuide(aGuidance: KNGuidance, aCitsGuide: KNGuide_Cits) {
    _naviView.didUpdateCitsGuide(aGuidance, aCitsGuide)
}
```

- C-ITS가 업데이트 될 경우 호출. citsGuide의 항목이 1개 이상 변경시 전달. 변경없는 항목은 이전과 동일한 객체로 전달


