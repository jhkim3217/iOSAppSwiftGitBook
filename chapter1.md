# 01 장

####1 앱에 Label 추가하기

![](1_1.png)

 
#### 2 How old are you? 


* IBOutlet 변수, IBAction 메소드



![](2_1.png)

    // ViewController.swift
    
    import UIKit
    
    class ViewController: UIViewController {
        
        @IBOutlet var label: UILabel!
        @IBOutlet var textField: UITextField!
        
        @IBAction func submit(sender: AnyObject) {
            
            print("Button tapped")
            label.text = textField.text
            
        }
        
        override func viewDidLoad() {
            super.viewDidLoad()
            print("Hello Kim!")
            
        }
    
        override func didReceiveMemoryWarning() {
            super.didReceiveMemoryWarning()
            // Dispose of any resources that can be recreated.
        }
    
    }


####3 Cat Year?
![](cat_year_1_1.png)
![](cat_year_2_1.png)
![](cat_year_3_1.png)

    //  ViewController.swift
    
    import UIKit
    
    class ViewController: UIViewController, UITextFieldDelegate {
        @IBOutlet var catAgeTextField: UITextField!
        @IBOutlet var resultLabel: UILabel!
        
        @IBAction func findAge(sender: AnyObject) { 
            
            var catAge = Int(catAgeTextField.text!)!
        
            catAge = catAge * 7
            
            resultLabel.text = "Your cat is \(catAge) in cat years"
            
        }
        
        override func viewDidLoad() {
            super.viewDidLoad()
            // Do any additional setup after loading the view, typically from a nib.
            catAgeTextField.delegate = self
            catAgeTextField.clearButtonMode = UITextFieldViewMode.Always
            
        }
    
        override func touchesBegan(touches: Set<UITouch>, withEvent event: UIEvent?) {
            
            self.view.endEditing(true)
            
        }
        
        func textFieldShouldReturn(textField: UITextField) -> Bool {
            
            catAgeTextField.resignFirstResponder()
            
            return true
            
        }
        
        func textFieldShouldClear(textField: UITextField) -> Bool {
            
            return true
            
        }
    
    }


---

[코딩 문제]




