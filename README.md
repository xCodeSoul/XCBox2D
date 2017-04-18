# XCBox2D
A Wrapper for Box2D API inside Cocos2D-X V3, Use Box2D in Cocos2DX Easily

# Why You Need This?
As you know Cocos2DX uses chipmunk 7 as built-in physics engine, also they provide a nice API to simplify usage of chipmunk physics Engine

But What if you love Box2D, Just Like me :), This Wrapper Will Give you what you want... This API Will let you use Box2D in Cocos2dX Scene, Plus A Nice API, just like Cocos2dx api for chipmunk.

# Installation of XCBox2D

Clone , or Download ZIP file of XCBox2D from github and Place (XCBox2DHelper) into Classes Folder of your Cocos2D-X Project

Simply, Add This Folder into your xcode project and now you ready to use XCBox2D

Note: Select Create Groups and Add them into Target of Project

# XCBox2D Class Creator

<img src="https://i.imgbox.com/QlcQNZGX.png" alt="image host"/>

This Creator will help easily create XCScene class, no need to dublicate HelloWorld Scene to Add Everything, Also this Creator will help to Create Subclass of XCSprite

Download XCBox2D Creator

 - Mac OS X ( <a href="#">Download</a> )
 - Windows ( <a href="#">Download</a> )
 - Linux ( <a href="#">Download</a> )

 How Using XCBox2D Class Creator

First of all, you jave to create your XCScene

1- Write your Class Name (Example: GameScene )

2- Choose The Super as XCScene

3- if you Want add settings like Enable Debug and Boundary and Contact events kust check them for World Gravity, just write your values

4- Choose Where To Save and Create Your Class

5- Move .h and .cpp files to Your Classes Folder

# **_Documentations_**

# XCScene in Depth

What you should know about this class, This class is inherit from cocos2d::Layer

So, you should forgot cocos2d::Layer, because without XCScene you will not able to use the API


**The Functions of XCScene**

XCScene has many functions to help you using Box2D more easier than normal Box2D API

  + **Set World Graviry**

```
gamescene->setBox2DWorldGravity( Vec2(0.0f, -9.8f) );
```

This Line for settting the World Gravity

+ **Enable Debug Mode**

```
gamescene->setBox2DWorldDebug(true);
```

if you want Enable Debug Mode, of course false will disable

+ **Boundary**

```
gamescene->setBoundary(BoundaryType::ALLSIDES);
```

Boundary in the Scene you have more Options for this, you can choose from the enum another types

**BoundaryType enum**

- BoundaryType::ALLSIDES)
- BoundaryType::LEFT)
- BoundaryType::RIGHT)
- BoundaryType::UP)
- BoundaryType::DOWN)

This will set Boundary around the Scene, good to prototyping

+ **World Update**

Each XCScene should have update function

So, don't forgot and don't remove it from this Scene

Important: don't remove calling the super inside Update Function

```
XCScene::update(dt);
```

Without this line, the world will not able to update itself.

# Your First Body

Now , lets try to add XCBox2D Body into our Scene With using this code - Put the code in initWithBox2D Function in your scene

    // Creating Sprite
    auto sprite = XCSprite::create("CloseNormal.png");
    
    sprite->setPosition( Vec2(visibleSize.width / 2, visibleSize.height / 2));
    
    this->addChild(sprite);

    // Creating Body
    
    auto body = XCBox2DPhysicsBody::createCircle(sprite->getContentSize().width / 2, BOX2DFIXTURE_DEFAULT);
    
    body->setBodyType(BodyType::Dynamic);

    sprite->setBox2DBody(body);

let's discuss the code, first of all we should create Sprite and add it into our Scene the important part is **XCSprite Class** which you always use to add your Sprites into scene

XCSprite Class usage same as cocos2d::Sprite Class but with API to use XCBox2D

So, We created the Sprite and position it on center and addit into our scene

Now, we will be able to to create our Box2D Body, don't think it's will be painful as Box2D API, long andan confused :)

XCBox2D will help you to Create Body Easily

**XCBox2DPhysicsBody Class**





