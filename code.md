# current-light-progress
//  Created by Joseph Lichtenstein on 9/23/19.
//  Copyright © 2019 Joseph Lichtenstein. All rights reserved.
//

import UIKit

class ViewController: UIViewController {
    @IBOutlet var `Switch`: UIButton!
    
    @IBOutlet var Rslider: UISlider!
    @IBOutlet var Gslider: UISlider!
    @IBOutlet var Bslider: UISlider!
    var l = Double()
    var lightOff = false
    var lightOn = true
    var r = Double()
    var g = Double()
    var b = Double()
    var red = CGFloat()
    var green = CGFloat()
    var blue = CGFloat()
    var light = CGFloat()
    override func viewDidLoad() {
        super.viewDidLoad()
        
        // Do any additional setup after loading the view.
    }

    @IBAction func rslide(_ sender: Any) {
        r = Double(Rslider.value)
        red = CGFloat(r)
        Switch.setTitle("color", for: .normal) ;
        Switch.setTitleColor(.magenta, for: .normal)
        view.backgroundColor = UIColor (red: red , green: green , blue: blue, alpha: light )
    }
    @IBAction func gslide(_ sender: Any) {
        g = Double(Gslider.value)
        green = CGFloat(g)
        Switch.setTitle("color", for: .normal) ;
        Switch.setTitleColor(.magenta, for: .normal)
        view.backgroundColor = UIColor (red: red , green: green , blue: blue, alpha: light )
    }
    @IBAction func bslide(_ sender: Any) {
        b = Double(Bslider.value)
        blue = CGFloat(b)
        Switch.setTitle("color", for: .normal) ;
        Switch.setTitleColor(.magenta, for: .normal)
        view.backgroundColor = UIColor (red: red , green: green , blue: blue, alpha: light )
    }
    @IBAction func OnOff(_ sender: Any) {
        lightOn.toggle()
        updateUI()
        lightOff.toggle()
    }
    func updateUI() {
        if lightOn {

            Switch.setTitle("on", for: .normal) ;
            Switch.setTitleColor(.black, for: .normal) ;
            r = 1.0
            g = 1.0
            b = 1.0
            l = 1.0
        view.backgroundColor = UIColor (red: red , green: green , blue: blue, alpha: light )
        }else{

            Switch.setTitle("off", for: .normal) ;
            Switch.setTitleColor(.yellow, for: .normal) ;
            r = 0.0
            g = 0.0
            b = 0.0
            l = 1.0
        view.backgroundColor = UIColor (red: red , green: green , blue: blue, alpha: light )
        }
        light = CGFloat(l)
        view.backgroundColor = UIColor (red: CGFloat(r) , green: CGFloat(g) , blue: CGFloat(b), alpha: light )


        

    }
}
