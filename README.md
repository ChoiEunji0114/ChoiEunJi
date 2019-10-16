## 01_seminar_helloworld

<img src="/screenshots/01_helloworld.png" width="200" height="400"> 

<br/>
<br/>

## 01_seminar_storyboard

<img src="/screenshots/01_storyboard_1.png" width="200" height="400"> <img src="/screenshots/01_storyboard_2.png" width="200" height="400"> 

- 버튼 클릭 >> cmd + drag&drop >> present modally 클릭

<br/>
<br/>


## 01_seminar_storyboard_2

- 객체 제어
```swift 
    @IBOutlet weak var titleLabel: UILabel!
     
    @IBAction func sayHello(_ sender: UIButton) {
        self.titleLabel.text = "SOPT!"
    }
```

<img src="/screenshots/01_storyboard2_1.png" width="200" height="400"> <img src="/screenshots/01_storyboard2_2.png" width="200" height="400"> 


<br/>
<br/>


## 01_supplement_UIcontrol

* UI Button states
    - Default : 누르지 않은 상태
    - Highlighted : 누른 상태
    - Selected : 버튼의 selected property 가 설정된 상태
    - Disabled : 버튼을 누를 수 없도록 설정된 상태 
    
<br/>

<img src="/screenshots/01_UIcontrol.png" width="200" height="400"> <img src="/screenshots/01_UIcontrol2.png" width="200" height="400"> 


<br/>
<br/>


## 01_supplement_image_asset

* image 추가
    - Assets.xcassets 에 이미지 파일 drag & drop
    
* button image 추가
    - type >> custom 선택
    - 각 state 별로 이미지 선택 
    

<img src="/screenshots/01_image2.png" width="200" height="400"> <img src="/screenshots/01_image1.png" width="200" height="400"> 


<br/>
<br/>

## 01_supplement_UIswitch

```swift 
    @IBOutlet weak var candleLabel: UILabel!
    @IBOutlet weak var candleImage: UIImageView!
    
    @IBAction func switchCtrl(_ sender: UISwitch) {
        if sender.isOn {
            self.candleLabel.text = "Candle is On"
            candleImage.image = UIImage(named: "candle-on")
        } else {
            self.candleLabel.text = "Candle is Off"
            candleImage.image = UIImage(named: "candle-off")
        }
    }
```

<img src="/screenshots/01_switch_on.png" width="200" height="400"> <img src="/screenshots/01_switch_off.png" width="200" height="400"> 


<br/>
<br/>


## 01_supplement_UIslider

```swift 
    @IBOutlet weak var sliderRed: UISlider!
    @IBOutlet weak var sliderGreen: UISlider!
    @IBOutlet weak var sliderBlue: UISlider!
    
    @IBAction func updateColor(_sender:UISlider){
        self.view.backgroundColor = UIColor.init(red: CGFloat(self.sliderRed.value), green: CGFloat(self.sliderGreen.value), blue: CGFloat(self.sliderBlue.value), alpha: 1.0)
    }

```

<img src="/screenshots/01_UIslider1.png" width="200" height="400"> <img src="/screenshots/01_UIslider2.png" width="200" height="400"> 


<br/>
<br/>


## 01_supplement_UISegmentController

- segment 값 전달하기

1. View Controller

```swift 
    @IBOutlet weak var leftRightSegControl: UISegmentedControl!
    var makeString: String!
    
    override func prepare(for segue: UIStoryboardSegue, sender: Any?) {
        let destVC = segue.destination as! SegControlViewController
        
        let situation: String! = leftRightSegControl.titleForSegment(at: leftRightSegControl.selectedSegmentIndex)
        
        destVC.title = situation
        
        makeString = situation
        makeString += " 선택됨"
        
        destVC.info = makeString
        destVC.selectedSegmentIndex = leftRightSegControl.selectedSegmentIndex
    }
```

2. SegControl View Controller

```swift 
    @IBOutlet weak var displayLabel: UILabel!
    @IBOutlet weak var leftRightSegControl: UISegmentedControl!
    
    var selectedSegmentIndex: Int!
    var info: String!
    
    override func viewDidLoad() {
        super.viewDidLoad()
        if let contentString = info{
            displayLabel.text = contentString
        }
        
        if let whichSelect = selectedSegmentIndex {
            leftRightSegControl.selectedSegmentIndex = whichSelect
        }
    }
```


<img src="/screenshots/01_leftsend.png" width="200" height="400"> <img src="/screenshots/01_leftselected.png" width="200" height="400"> <img src="/screenshots/01_rightsend.png" width="200" height="400">  <img src="/screenshots/01_rightselected.png" width="200" height="400"> 





## 01_hw_instagram
```swift 
    var isClicked : Bool = false
   
    @IBAction func btnClick(_ sender: Any) {
        
        if isClicked==false {
            self.likeLabel.text = "sopt.iOS.Lover  님이 좋아합니다."
            heartBtn.setImage(UIImage(named: "hearrt-fill"), for: .normal)
            isClicked = true
        } else {
            self.likeLabel.text = ""
            heartBtn.setImage(UIImage(named: "heart"), for: .normal)
            isClicked = false
        }  
    }
```

<img src="/screenshots/01_insta.png" width="200" height="400"> <img src="/screenshots/01_insta2.png" width="200" height="400">

<br/>
<br/>


