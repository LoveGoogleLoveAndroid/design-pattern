## design-pattern
common design patterns in Android.   

* [六种关系](#六种关系)
* [六大原则](#六大原则)
* [三种类型](#三种类型)
* [单例模式-Singleton](#单例模式-singleton)
* [观察者模式-Observer](#观察者模式-observer)
* [享元模式-FlyWeight](#享元模式-flyweight)
* [外观模式-Facade](#外观模式-facade)
* [桥接模式-Bridge](#桥接模式-bridge)
* [装饰模式-Decorator](#装饰模式-decorator)
* [适配器模式-Adapter](#适配器模式-adapter)
* [组合模式-Composite](#组合模式-composite)
* [代理模式-Proxy](#代理模式-proxy)
* [中介者模式-Mediator](#中介者模式-mediator)
* [访问者模式-Visitor](#访问者模式-visitor)
* [模板方法模式-Template](#模板方法模式-template)
* [迭代器模式-Iterator](#迭代器模式-iterator)
* [备忘录模式-Memoto](#备忘录模式-memoto)
* [解释器模式-Interpreter](#解释器模式-interpreter)
* [命令模式-Command](#命令模式-command)
* [责任链模式-Chain of Responsibility](#责任链模式-chain-of-responsibility)
* [状态模式-State](#状态模式-state)
* [策略模式-Strategy](#策略模式-strategy)
* [工厂方法模式-Factory Method](#工厂方法模式-factory-method)
* [抽象工厂模式-Abstract Factory](#抽象工厂模式-abstract-factory)
* [原型模式-Prototype](#原型模式-prototype)
* [创建者模式-Builder](#创建者模式-builder)

## 六种关系
1. 泛化关系-Generalization:是一种继承关系，表示一般与特殊的关系，它指定了子类如何特化父类的所有特征和行为。例如：老虎是动物的一种，即有老虎的特性也有动物的共性。带三角箭头的实线，箭头指向父类
2. 实现关系-Realization：是一种类与接口的关系，表示类是接口所有特征和行为的实现。带三角箭头的虚线，箭头指向接口
3. 关联关系-Association：是一种拥有的关系，它使一个类知道另一个类的属性和方法；如：老师与学生，丈夫与妻子关联可以是双向的，也可以是单向的。双向的关联可以有两个箭头或者没有箭头，单向的关联有一个箭头。带普通箭头的实心线，指向被拥有者
4. 聚合关系-Aggregation：是整体与部分的关系，且部分可以离开整体而单独存在。如车和轮胎是整体和部分的关系，轮胎离开车仍然可以存在。 聚合关系是关联关系的一种，是强的关联关系；关联和聚合在语法上无法区分，必须考察具体的逻辑关系。带空心菱形的实心线，菱形指向整体
5. 组合关系-Composition：是整体与部分的关系，但部分不能离开整体而单独存在。如公司和部门是整体和部分的关系，没有公司就不存在部门。 组合关系是关联关系的一种，是比聚合关系还要强的关系，它要求普通的聚合关系中代表整体的对象负责代表部分的对象的生命周期。带实心菱形的实线，菱形指向整体
6. 依赖关系-Dependency：是一种使用的关系，即一个类的实现需要另一个类的协助，所以要尽量不使用双向的互相依赖。带箭头的虚线，指向被使用者

## 六大原则
1. 单一职责原则：一个类中应该是一组相关性很高的函数、数据的封装。一个类应该仅有一个引起它变化的原因，两个完全不一样的功能就不应该放在一个类中。如果一个类承担的职能过多，这些职责将会耦合到一起，一个职责的变化可能会削弱或抑制这个类完成其他职责的能力，这种耦合会导致脆弱的设计，当变化发生时，设计会遭受意想不到的破坏
2. 开放封闭原则：对修改封闭，对扩展放开。如何面对需求的改变才能让设计保持相对稳定，从而使得系统可以在第一个版本以后不断推出新的版本，就必须坚持开放封闭原则；开始编写代码时，假设不会有变化，当变化发生时，就应创建抽象来隔离以后发生的同类变化，面对需求，对程序的改动是通过增加代码进行的，而不是更改现有的代码；开放封闭原则是面向对象设计的核心所在，遵循这个准则可实现代码可维护、可扩展、可复用、灵活性好
3. 里氏替换原则：抽象和继承；所有引用基类的地方必须能透明的使用其子类的对象，而且察觉不出基类对象和子类对象的区别，只有当子类可以替换掉基类，软件的功能不受影响时，基类才能被真正复用，而子类才能在基类基础上增加新的行为，由于有了里氏替代原则，才使得开放封闭成了可能；正是由于子类型的可替代性才使得使用父类型的模块在无需修改的情况下就可以扩展
4. 依赖倒置原则：高层模块不应该依赖底层模块，两者都应该依赖抽象，抽象不应该依赖细节，细节应该依赖抽象。
5. 接口隔离原则：将大接口改成多个小接口。
6. 迪米特原则：也称为最少知识原则，一个对象应该对另一个对象有最少的了解

## 三种类型
1. 创建型模式5种：单例模式，抽象工厂模式，工厂模式，原型模式，建造者模式。
（口诀：单原建造者，东西二厂）
2. 结构型模式7种：适配器模式，桥接模式，装饰模式，组合模式，外观模式，享元模式，代理模式。
（口诀：一器一桥一元一代理；装饰组合外观）
3. 行为型模式11种：观察者模式，中介者模式，访问者模式，解释器模式，迭代器模式，备忘录模式，责任链模式，状态模式，策略模式，命令模式，模板模式。
（口诀：三者两器、一录一链一模板，状态策略命令）

## 单例模式-Singleton
构造函数不对外开放，只有一个静态方法返回单例类对象，需确保在多线程下保持单例类对象只有一个，并在反序列化时不会重新构建对象  
* 懒汉模式：使用时才初始化，一定程度上节约资源，但是第一次加载需要实例化，且每次调用需要同步，开销较大，不建议使用  
* Double Check Lock模式：第一层判断为了不必要的同步，第二层为了在null的情况下创建实例；优点是解决了资源消耗，多余同步和线程安全问题，但是在某些情况下存在DCL失效情况  
* 静态内部类模式：线程安全，也能保证单例对象的唯一性，同时延迟了单例的实例化，是推荐的实现方式  
还可以通过枚举和容器实现  

Android：`WMS，AMS，LayoutInflater Service，InputMethodManager Service`   等都是以容器方式创建  
```
private static final HashMap<String, ServiceFetcher> SYSTEM_SERVICE_MAP =
            new HashMap<String, ServiceFetcher>();
// register map
    private static void registerService(String serviceName, ServiceFetcher fetcher) {
        if (!(fetcher instanceof StaticServiceFetcher)) {
            fetcher.mContextCacheIndex = sNextPerContextServiceCacheIndex++;
        }
        SYSTEM_SERVICE_MAP.put(serviceName, fetcher);
    }
// initialization just once
        registerService(LAYOUT_INFLATER_SERVICE, new ServiceFetcher() {
                public Object createService(ContextImpl ctx) {
                    return PolicyManager.makeNewLayoutInflater(ctx.getOuterContext());
                }});
// get the instance                
    public Object getSystemService(String name) {
        ServiceFetcher fetcher = SYSTEM_SERVICE_MAP.get(name);
        return fetcher == null ? null : fetcher.getService(this);
    }
```

## 观察者模式-Observer
观察者模式定义了一个一对多的依赖关系，让一个或多个观察者对象监听一个主题对象。当被观察者状态发生改变时，需要通知相应的观察者，使这些观察者对象能够自动更新  
* 事件委托：观察者和通知者互相不知道，由客户端来决定通知谁  
* 事件总线：在一个Activity发送广播，另一个Activiy接收，比较麻烦，如果传递数据是类对象，还要序列化；在一个Activity，定义一个子线程处理任务，完成后必须用Handler或AsyncTask来更新UI，也比较麻烦；事件总线可以进一步简化Activity，Fragment，Service等组件间的交互，很大程度上降低了它们的耦合  

Android：`Broadcard Receiver`的注册机制；ListView里面Adapter的方法`notifyDataSetChanged`  


## 享元模式-FlyWeight
对象池的一种实现，适用于存在大量重复对象的场景，可显著的减少对象创建数量减少内存使用  
* 可共享的、不变的状态为内部状态，经典实现会将内部状态作为键，对象作为值进行MAP存储，不可共享的、易变的状态为外部状态
* 需要分离内部、外部状态，使得系统变得复杂，而且外部状态不会随着内部状态改变而改变，会导致系统逻辑混乱  

Android：`Message m = obtain();`对象池，并非享元模式的经典实现，简单的单链表    
如果对象池为空创建对象，否则从对象池获取消息并删除结点  
```
    public static Message obtain() {
        synchronized (sPoolSync) {
            if (sPool != null) {
                Message m = sPool;
                sPool = m.next;
                m.next = null;
                m.flags = 0; // clear in-use flag
                sPoolSize--;
                return m;
            }
        }
        return new Message();
    }
```
当消息被消费（处理）后，则重新加入对象池
```
    void recycleUnchecked() {
        // Mark the message as in use while it remains in the recycled object pool.
        // Clear out all other details.
...
        synchronized (sPoolSync) {
            if (sPoolSize < MAX_POOL_SIZE) {
                next = sPool;
                sPool = this;
                sPoolSize++;
            }
        }
    }
```
## 外观模式-Facade
封装API的常用手段，要求子系统的外部与其内部的通信必须通过一个统一的对象进行  
* 为复杂子系统提供一个简单接口，对外隐藏子系统的具体实现、隔离变化；如果构建一个层次结构的子系统，使用外观模式定义子系统每层的入口点，如果子系统之间是互相依赖的，可以让他们仅仅通过外观模式的接口进行通信  
* 外观类接口会增加，而且没有遵循开闭原则，当业务出现变更，可能需要修改外观类接口  

Android：`ContextImpl`，Activity（Service，Broadcast Receiver等）也是一个Context，其具体实现是ContextImpl，通过ContextWrapper、ContextThemeWrapper封装，如startActivity等接口最终实现是在ContextImpl中  

```
Context appContext = createBaseContextForActivity(r, activity);
....
// 将Application, ContextImpl, Activity联系起来
activity.attach(appContext, this, getInstrumentation(), r.token,
                        r.ident, app, r.intent, r.activityInfo, title, r.parent,
                        r.embeddedID, r.lastNonConfigurationInstances, config,
                        r.referrer, r.voiceInteractor);
....
// mBase为ContexImpl对象，Activity内部持有了ContextImpl的引用
    protected void attachBaseContext(Context base) {
        if (mBase != null) {
            throw new IllegalStateException("Base context already set");
        }
        mBase = base;
    }      
// 实际会调用ContextImpl的startActivity
    public void startActivity(Intent intent) {
        mBase.startActivity(intent);
    }


```

## 桥接模式-Bridge
将抽象部分和实现部分分离，让他们都能独立的进行变化，事实上，任何多维度变化或树型之间的耦合都可以通过桥接模式来解耦  
* 如果一个系统需要在构件的抽象变化角色和具体变化角色之间增加更多的灵活性，避免在两个层次之间建立静态的继承关系，可以通过桥接模式在抽象层建立一个关联关系  
* 易于理解，却难以设计，所以应用不多，一个重要的原因是不容易对于抽象和实现恰到好处的进行分离  

Android：`TextView, Button, CheckBox`等定义控件基本属性和行为的View和真正绘制他们的功能实现类如`DisplayList，HardwareLayer，Cavas`之间可以看做是桥接模式的应用，Adapter和AdapterView之间，Window和WindowManager之间也是  

## 装饰模式-Decorator
使用一种对客户端透明的方式来动态的扩展对象的功能，同时也是继承关系的一种替代方案之一  
* 使用场景：动态的给对象增加额外的职责，就增加功能来说，比生成子类更加灵活  
* 和代理模式容易混淆，代理模式是给一个对象提供一个代理对象，并由代理对象来控制对原有对象的引用，但不对对象本身的功能进行增强  

Android：`ContextWrapper`，ContextImpl是上帝对象Context的具体实现，ContextWrapper则扮演装饰者的角色，持有一个Context的对象  
```
public class ContextWrapper extends Context {
    Context mBase;
    public ContextWrapper(Context base) {
        mBase = base;
    }
....
    @Override
    public void startActivity(Intent intent) {
        mBase.startActivity(intent);
    }
```

## 适配器模式-Adapter
把一个类的接口变换为客户端所期待的另一种接口，从而使原本因接口不匹配而无法在一起工作的两个类可以在一起工作，分为类适配器和对象适配器，类适配器需要多重继承支持，只讨论对象适配器模式    
* 如果系统的数据和行为都正确，只有接口不符时，或系统需要复用现有的类，而此类的接口不符合系统的需要，就可以使用适配器模式，也可以调用自己开发的功能，扩展系统功能
* 过多的使用会让系统非常凌乱，不容易整体把握，明明调用的是A，内部又被适配成了B；如果事先能预防接口不同的问题，不匹配的问题就不会发生，在有小的接口不统一发生问题时，及时重构，问题不至扩大，只有碰到无法改变原有设计和代码的情况下，才考虑适配

Android：`ListView中的Adapter`，输入（item view自定义视图）有无数种，通过增加一个Adapter来隔离变化，将ListView需要的关于item view接口抽象到Adapter对象中，并在ListView内部调用Adapter这些接口完成布局等操作，用户只要实现Adapter接口，就能保证有统一的输出  
## 组合模式-Composite
也称部分-整体模式，将一组相似的对象看作一个对象处理，并根据一个树形结构来组合对象，然后提供一个统一的方法去访问相应的对象，以此忽略掉对象与对象集合之间的差别，比较典型的例子是公司的组织结构树形图  
* 可以清楚的定义分层的复杂对象，让高层模块忽略层次差异，方便对整个层次结构进行控制，高层模块可以一致的使用一个组合结构或者其中单个对象，不必关心处理的是哪个，简化了高层模块的代码，增加新的枝干和叶节点都很方便，符合开闭原则，为树形结构的面向对象提供了一种灵活的解决方案，通过对枝干对象和叶对象的递归组合，可以形成复杂的树形结构，但对其控制却很简单
* 在新增构件时不好对枝干中的构件类型进行限制，不能依赖类型系统来施加这些约束，因为他们来自相同的抽象层，必须通过类型检查来实现，这个实现过程较为复杂

Android：`View和ViewGroup的嵌套组合`，ViewGroup或继承自ViewGroup的LinearLayout等控件作为容器可以包含TextView或其子类如Button、CheckBox等，然后反之不行，但是它们都继承自统一的抽象类View，且Android此处实现为安全的设计模式，若根据依赖倒置原则，按照透明的组合模式，叶节点（Button、TextView）和枝干节点（ViewGroup、LinearLayout）应有相同的结构（全部继承并实现根部抽象类View的方法），而叶节点不支持的方法则在类中进行判断识别   

## 代理模式-Proxy
也称委托模式，为其他对象提供一种代理以控制对这个对象的访问，当无法或不想直接访问某个对象或访问某个对象存在困难时可以通过一个代理对象来间接访问，为了保证客户端使用的透明性，委托对象和代理对象需要实现相同的接口，代理模式在现实中比比皆是，如让同事帮忙打饭，让律师帮忙打官司等  
* 静态代理：代理者的代码由程序猿或通过一些自动化工具生成固定的代码再对其编译，运行前代理类的class编译文件就已经确定，只能为给定接口下的实现类做代理，如果接口不同就需要重新定义不同的代理类，较为复杂，但是更符合面向对象原则  
* 动态代理：通过反射动态的生成代理者的对象，在code阶段不需要知道代理谁，在Java中可以通过动态代理接口InvocationHnadler实现，通过一个代理类来代理多个被代理类，其实质是对代理者与被代理者进行解耦    
* 远程代理、虚拟代理、保护代理、智能引用这四种可独自应用于静态代理和动态代理，两者各自独立对的变化  

Android：`ActivityManagerProxy代理类`，其代理的是ActivityManagerNative的子类ActivityManagerService，AMS是系统级服务并运行在独立的进程空间，而ActivityManagerProxy也运行于自己独立的进程空间，因此它们的通信通过Binder以跨进程方式进行，其实质是远程代理  


## 中介者模式-Mediator
也称调解者模式，包装了一系列对象相互作用的方式，使得这些对象不必相互明显作用，从而使他们可以松散耦合，将多对多的相互作用转化为一对多的相互作用，将系统从网状结构变成以调停者为中心的星型结构，降低了系统的复杂度，提高了可扩展性  
Android：`Binder机制`、锁屏功能的`KeyguardViewMediator`定义了很多管理器（音频、闹钟、搜索...），也定义了很多方法来处理这些管理器的状态  


## 访问者模式-Visitor
封装一些作用于某种数据结构中的各元素的操作，可以在不改变这个数据结构的前提下定义作用于这些元素的新操作，一种将数据结构和数据操作分离的设计模式，是23种常见设计模式种最复杂的一个，使用频率不高，可一旦需要，那就是真的需要了；适用于对象结构比较稳定，但是经常需要在此对象结构上定义新的操作，需要对一个对象结构的对象进行很多不同并且不相关的操作，且要避免这些操作污染这些类，也不希望增加新操作时修改类    
* 各角色职责分离，符合单一职责原则，具有优秀的扩展性，使得数据结构和作用于其上的操作解耦，操作集合可以独立变化
* 具体元素需要对访问者公布细节，违反了迪米特法则，具体元素变更时修改成本很大，违反了依赖倒置原则，为了区别对待，依赖了具体类

Android：`注解`  


## 模板方法模式-Template
定义一个操作中算法的框架，流程封装，将某个固定的流程封装到一个final函数，而将一些延伸步骤延迟到子类中，使得子类可以不改变一个算法的结构即可定义该算法的某些特定步骤  
* 多个子类有公有的方法且基本逻辑相同；重要复杂的算法可以把核心算法设计为模板方法，周边功能由子类实现；重构时，模板方法是常用模式，可以把相同代码抽取到父类，然后通过钩子函数约束其行为
* 会带来代码阅读的难度，会让用户觉得难以理解

Android：`AsyncTask中多个方法的固定执行步骤 Execute->onPreExecute->donInBackground->onPostExecute`，`Activity的生命周期函数执行顺序 onCreate->onStart->onResume` 等  


## 迭代器模式-Iterator
也称游标模式，提供了一种方法顺序访问一个容器对象的各个元素，又不需要暴露该对象的内部表示，支持以不同方式去遍历一个容器对象，弱化了容器类与遍历算法之间的关系，几乎每种高级语言都有内置实现，开发者已经很少去实现了  


Android：`数据库查询中的Cursor游标`，该游标实质是一个具体的迭代器，可用来遍历数据库查询结果集  


## 备忘录模式-Memoto
在不破坏封闭前提下，捕获一个对象的内部状态，并在对象之外保存这个状态，以后可将对象恢复到原先状态
* 实现了信息的封装，使得用户无需知道状态的保存细节，多次保存可实现撤销、重做功能
* 如果需要保存的对象过多，易消耗资源

Android：`onSaveInstanceState和onRestoreInstanceState`，当系统存在“未经许可”时销毁了Activity，比如按了HOME键、长按HOME选择其他程序、按POWER关闭屏幕、切换屏幕方向、电话接入等，onSaveInstanceState就会执行  


## 解释器模式-Interpreter
定义了一个表达式接口，通过该接口解释一个特定的上下文，实际中使用较少，我们很少需要自己构造一个语言的语法  
* 灵活的扩展性，对文法规则进行扩展延伸时，只需增加相应的非终结符解释器，在构建抽象语法树时，使用新增的解释器对对象进行解析即可
* 对于每条文法都要对应增加至少一个解释器，会生成大量的类，导致维护困难，复杂的文法不推荐使用解释器模式

Android：`PMS对AndroidMenifest.xml的解析`

## 命令模式-Command
将一个请求封装成一个对象，从而可以用不同的请求对客户进行参数化，对请求排队或记录请求日志，以及支持可撤销的操作  
* 更弱的耦合性，更灵活的控制性和更好的扩展性，可以方便的对命令进行记录、撤销和重做，其应用并不局限于GUI
* 充分体现了几乎所有设计模式的通病，即大量衍生类的创建

Android：`事件机制中底层逻辑对事件的转发处理`

## 责任链模式-Chain of Responsibility
使多个对象都有机会处理请求，从而避免了请求的发送者和接收者之间的耦合关系，将这些对象连成一条链，沿着这条链传递请求，直到有对象处理为止     
* 多个对象可以处理一个请求，在请求处理者不明确的情况下向其中一个处理者提交请求
* 对链中请求处理者的遍历，如果处理者太多，势必影响性能，特别是一些递归调用，需慎重  

Android：`事件的分发处理`  

## 状态模式-State
状态模式的行为由状态来决定，不同的状态下有不同的行为，主要解决当控制一个对象状态转变的条件表达式过于复杂，把状态的判断逻辑迁移到表示不同状态的同一系列类中  
* 状态模式和策略模式的结构几乎完全一样，但它们的目的、本质却完全不同，状态模式的行为是平行的、不可替换的，策略模式的行为是彼此独立的、可以替换的；状态模式把对象的行为包装在不同的状态对象里，每个状态对象都有一个共同的抽象状态基类，状态模式的意图是让一个对象在其内部状态改变的时候其行为也随之改变  
* 如果代码中大量的if-else或switch-case语句，则应重构，如果一个对象的行为取决于它的状态，并且它必须在运行时刻根据状态改变它的行为时，可以考虑使用状态模式，它提供更好的方法来组织与特定状态相关的代码，将繁琐的状态判断转换为结构清晰的状态类族

Android：`WIFI管理中的开关`

## 策略模式-Strategy
策略模式定义了一系列算法，并将每个算法封装起来，他们之间可以互相替换，针对同一问题的多种处理方式，仅仅是具体行为有差别   

Android：`属性动画的时间插值器` 等等  

## 工厂方法模式-Factory Method
定义一个用于创建对象的接口，让子类决定实例化哪个类，在任何需要生成复杂对象的地方都可以使用工厂方法模式，有时候可以用反射的方式更简洁的生产具体产品对象，此时只需在工厂方法的参数列表传入一个Class类来决定是哪个产品类  

Android：`ArrayList和HastSet的iterator相当于一个工厂方法`，List和Set都继承于Collection接口，而Collection又继承于Iterable接口，其中唯一的方法iterator专为new对象而生，`onCreate也是一个工厂方法，其中的setContentView`方法可以传入不同的布局来初始化  

## 抽象工厂模式-Abstract Factory
为创建一组相关或者是相互依赖的对象提供一个接口，而不需要指定他们的具体类  
* 客户端使用抽象工厂创建需要的对象，而根本就不知道具体的实现者是谁，客户端只是面向产品的接口编程，同时基于接口和实现的分离，使得在切换产品类时更加灵活容易
* 类爆炸性的增加，不太容易扩展新的产品类，每当增加一个产品类就需要修改抽象工厂，那么所有的具体工厂类都得修改  

Android：不太多见，`MediaPlayer的四个Factory会生成四个不同的MediaPlayer的基类，而这四个类都继承于MediaPlayerBase`    
```
sp<MediaPlayerBase> MediaPlayerFactory::createPlayer(
...
    p = factory->createPlayer(pid);
...
class NuPlayerFactory : public MediaPlayerFactory::IFactory {
...
class TestPlayerFactory : public MediaPlayerFactory::IFactory {
...

```

## 原型模式-Prototype
用户从一个样板对象中复制出一个内部属性一致的对象，这个过程称为克隆或者拷贝  
* 通过new产生一个对象需要非常繁琐的数据准备或访问权限，类的初始化需要消耗很多资源，如数据、硬件等，此时可以使用原型模式避免这些消耗
* 保护性拷贝：一个对象需要提供给其他对象访问，而且各个调用者可能修改其值，此时可以使用原型模式
* 通过实现Cloneable接口的原型模式在调用clone方法构造实例时不一定比new速度更快，只有new的成本过高时，才通过clone，实现原型模式也不一定非要实现Cloneable接口；clone方法并不在Cloneable接口，而是在Object方法中，Cloneable是个标记接口，只表明这个类的对象可拷贝，如果没有实现Cloneable接口却调用clone方法则抛出异常  
* 原型模式的实现即C++或者Java中的浅拷贝（影子拷贝，类中无指针或对象引用成员）或深拷贝；用new构造对象的方式即C++中的拷贝构造函数  
* 本质是对象拷贝，使用原型模式可以解决构建复杂对象的资源消耗问题，在某些场景下可以提升创建对象的效率  

Android：`ArrayList和Intent中的clone方法` 等等  

## 创建者模式-Builder
讲一个复杂对象的构建与它的表示分离，使得同样的构建过程可以创建不同的表示，使用场景较多：  
* 相同的方法，不同的执行顺序，产生不同的事件结果时
* 多个部件或零件，都可以装配到一个对象中，但是产生的运行结果又不相同
* 产品类非常复杂，或者产品类中的调用顺序不同产生了不同的作用
* 当初始化一个对象特别复杂，如参数多，且很多参数都有默认值  

Android：非常常见，`AlertDialog.Builder` 等等  
