# JSObject-Class_ArraysOfData
JavaScript Object, Class data. Create a multiple object that push data array into object setter and getter JS.

```JS
 // Developer Object !
 class Developer {

  constructor(name, yearsExperience) {

    this.name = name;
    this.yearsExperience = yearsExperience;

  }

  // Method getName of Developer
  getName = () => { return this.name; }

  // Method Years of Experience of Developer
  getYearsExperience = () => { return this.yearsExperience; }

 } 
```

```JS 
 // Create NEW DEVELOPER !
 const dev1 = new Developer('Niel', 6 );
 const dev2 = new Developer('NielOffice', 7 );
 
 // Check Developers!
 console.log( dev1, dev2 );

 // Result 
 Developer {name: 'Niel', yearsExperience: 6, getName: ƒ, getYearsExperience: ƒ} 
 Developer {name: 'NielOffice', yearsExperience: 7, getName: ƒ, getYearsExperience: ƒ}
```
 
```JS
 // Experts 
 class Experts {
 
  // Expertise is the ability
  // The Experts is the objects
  constructor(expertise, experts ) {
     
    this.expertise  = expertise;
    this.experts = experts;
  }
  
  // Setter or add new Experts
  // push to array this.experts
  addExperts = (experts) => { return this.experts.push(experts); } 

  // Getter 
  // Get all expert
  getExperts = () => { return this.experts; }

 }
```
 
```JS
 // Create two object Developers 
 // Expertise is Web Developer
 const experts = new Experts('Web Developer', [dev1, dev2] ); // NEW DEVs
 // Checking objects
 console.log(experts);

```

```JS
 // Console.log() | Result 
 Experts {expertise: 'Web Developer', experts: Array(2), addExperts: ƒ, getExperts: ƒ}
 addExperts : (experts) => { return this.experts.push(experts); }
 expertise : "Web Developer"
 experts : Array(2)
  0 : Developer {name: 'Niel', yearsExperience: 6, getName: ƒ, getYearsExperience: ƒ}
  1 : Developer {name: 'NielOffice', yearsExperience: 7, getName: ƒ, getYearsExperience: ƒ}
 length : 2
 [[Prototype]] : Array(0)
 getExperts : () => { return this.experts; }
 [[Prototype]] : Object
```
 
```JS 
 // add new expert
 const dev3 = new Developer('John', 8 ); 
 // set expert
 experts.addExperts(dev3);

 // check new added expert
 console.log(experts.getExperts());
```
 
```JS
 // Console.log() | Result 
 (3) [Developer, Developer, Developer]
  0 : Developer {name: 'Niel', yearsExperience: 6, getName: ƒ, getYearsExperience: ƒ}
  1 : Developer {name: 'NielOffice', yearsExperience: 7, getName: ƒ, getYearsExperience: ƒ}
  2 : Developer {name: 'John', yearsExperience: 8, getName: ƒ, getYearsExperience: ƒ}
 length : 3
 [[Prototype]] : Array(0)
```

```JS
// Bonus handling static object
// Iterate Object : https://github.com/nielsoffice/JSObject
  const collections = experts.experts;
  
  console.log(collections);

  collections.forEach( ( element , index ) => {
     console.log( index +' : '+ element.name ); // Get index and names
  });

// Console.log | Result 
(3) [Developer, Developer, Developer]
 0: Developer {name: 'Niel', yearsExperience: 6, getName: ƒ, getYearsExperience: ƒ}
 1: Developer {name: 'NielOffice', yearsExperience: 7, getName: ƒ, getYearsExperience: ƒ}
 2: Developer {name: 'John', yearsExperience: 8, getName: ƒ, getYearsExperience: ƒ}
length: 3[[Prototype]]: Array(0)
// index and names
 0 : Niel
 1 : NielOffice
 2 : John
```

 This is how to create an static object and new object that push on existing without instantiate class. 
 This will helps when you are collecting a static data that you needs in order to manipulate for whatever reason to achive your web application goal interface or interactive. 
 This how you can easily maintain your code clean and easy. 
 
 <br /> JS Constructor property as setter method | Getter and Setter 
 
 ```HTML
 <html><head><style> 
  </style></head>
  
  <body id="app-id">
  
  <div id="elemTargeta" class="cons">
    <p>Demo Content...</p>
  </div>
  
  <script id="app-data">
    
    class Developer {
      
      constructor(name,specialty) {
        this.settingFullName  = name;
        this.specialty = specialty;
      }
    
      get info() {

        return this._settingFullName + ' : ' + this.specialty;

      }

      // Setter using a property name !
      // Once we use a property name as method name for a "SETTER" here in JS
      // the param or argument will recognize as we pass the value from the property
      // ex this.proName = value
      // as we use In setter it's going to be like proName(value);
      // so the  settingFullName method stand for property name and the "fn" param is stand 
      // as value from construction! 
      // FROM:  this.settingFullName  = settingFullName;
      // TO:  this.settingFullName(fn);
      set settingFullName(fn) {
        // If you get wondering where is the "fn" came from that is a value that we pass
        // on proerty from construction argument!
        if(fn.includes(' ') === true ) { // we check if there is a space to the fn or alue that we pass on constructor
          // then we will execute this as it is true or having space! 
          return this._settingFullName = fn; 
        } else {
          alert('Please enter your full name with space');
        }
     }
     
      // as we use the property name as method name here in JS in order this to work once 
      // we invoke inside of method we have to add or  put "_" underscore before it's name
      // ex. _settingFullName 
      get gettingFullName() {
       // exactly like: this._settingFullName;
       return this._settingFullName;
      }

    }

    // Try to remove space for name and last name error alert!
    const newObjClass = new Developer('Niel Fernandez', 'Web Developer');    
    console.log(newObjClass);
    
    // invoke info method to check if the constructor works!
    const getInfo = newObjClass.info;
    console.log(getInfo);

    // Try to remove space for name and last name error alert!
    // setter | newObjClass.settingFullName = 'Niel Fernandez';
    // const setterName = newObjClass.settingFullName = 'Niel Fernandez';
    // console.log('SETTER : '+setterName); // for demo checking only!

    // Getter is now rely on constructor!
    const gettingFullName = newObjClass.gettingFullName;
    console.log('GETTER : ' + gettingFullName);
   </script>
  
  </body></html>
 ```
 
 ```JS
 // console.log() | result 
Developer {_settingFullName: 'Niel Fernandez', specialty: 'Web Developer'}
specialty: "Web Developer"
_settingFullName: "Niel Fernandez"
gettingFullName: (...)
info: (...)
[[Prototype]]: Object
constructor: class Developer 
gettingFullName: (...)
info: (...)
get gettingFullName: ƒ gettingFullName()
get info: ƒ info()
set settingFullName: ƒ settingFullName(fn)
[[Prototype]]: Object
--------------------------
Niel Fernandez : Web Developer
GETTER : Niel Fernandez
 ```
 
