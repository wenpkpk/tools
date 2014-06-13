tools
=====

Xcode代码片段共享
使用：
    git下载完，放在系统~/Library/Developer/Xcode/UserData/CodeSnippets


变量声明
=====

1.@propertyAssign ------>声明一个assign变量
-----------------------------------
###
	@property(nonatomic, assign) 
###

2.@propertyStrong ------>声明一个strong变量
-----------------------------------
###
	@property(nonatomic, strong) 
###

3.@propertyWeak ------>声明一个weak变量
-----------------------------------
###
	@property(nonatomic, weak) 
###
4.id ------>声明delegate
-----------------------------------
###
	id____[protocol]____ ____[delegate]____;
###



变量定义
=====

1.myMutableArray ------>定义一个可变数组array
-----------------------------------
###
    NSMutableArray *____[mutableArray]____ = [NSMutableArray array];
###

2.myMutableDictionary ------>定义一个可变字典dict
-----------------------------------
###
    NSMutableDictionary *____[mutableDict]____ = [NSMutableDictionary dictionary];
###

3. myAlertView ------>定义一个uialertView
-----------------------------------
###
    UIAlertView *alert = [[UIAlertView alloc] initWithTitle:____[@“title”]____ message:____[message]____ delegate:self cancelButtonTitle:@"取消" otherButtonTitles: @"确定",nil];
    
    alert.delegate = ____[nil]____;
    [alert show];
###

4.myCell ------>创建cell
-----------------------------------
###
	static NSString *cellIdentifier = ____[@"cellIdentifier"]____;
	UITableViewCell *cell = [tableView dequeueReusableCellWithIdentifier:cellIdentifier];

	if (!cell)
	{
    		cell = [[UITableViewCell alloc] initWithStyle:UITableViewCellStyleDefault reuseIdentifier:cellIdentifier];
	}
###



函数定义
=====

1.numberOfRowsInSection ------>返回TableView的rows数量
-----------------------------------
###
    - (NSInteger)tableView:(UITableView *)tableView numberOfRowsInSection:(NSInteger)section
    {
        int numberOfRows = 0;
        
        ____[code]____
        
        return numberOfRows;
    }
###

2.numberOfSectionsInTableView ------>返回TableView的sections数量
-----------------------------------
###
    - (NSInteger) numberOfSectionsInTableView:(UITableView *)tableView
    {
        int numberOfSections = 1;
        
        ____[code]____
        
        return numberOfSections;
    }
###

3.cellForRowAtIndexPath	------>cell
-----------------------------------
###
	- (UITableViewCell *)tableView:(UITableView *)tableView cellForRowAtIndexPath:(NSIndexPath *)indexPath
	{
   		 ____[UITableViewCell]____ *cell = [tableView dequeueReusableCellWithIdentifier:____[@"cell"]____];
    	
   		 if (nil == cell)
   	 	{
      			  cell = [[UITableViewCell alloc]initWithStyle:UITableViewCellStyleDefault reuseIdentifier:____[@"cell"]____];
  	 	}
    
    		____[code]____
    
   		 return cell;
	}
###

4.heightForHeaderInSection ------>返回TableView的SectionHeader的高度
-----------------------------------
###
    - (CGFloat)tableView:(UITableView *)tableView heightForHeaderInSection:(NSInteger)section
    {
        float height = 0.0f;
        
        ____[code]____
        
        return height;
    }
###

5.heightForRowAtIndexPath ------>返回TableView的cell的高度
-----------------------------------
###
    - (CGFloat)tableView:(UITableView *)tableView heightForRowAtIndexPath:(NSIndexPath *)indexPath
    {
        float height = 0.0f;
        
        ____[code]____
        
        return height;
    }
###

6.clicked ------>按钮事件
-----------------------------------
###
	- (void)____[btn]____Clicked:(id)sender
	{
    
	}
###

7.dealloc ------>取消监听的dealloc
-----------------------------------
###
	-(void)dealloc
	{
   		 [NSObject cancelPreviousPerformRequestsWithTarget:self];
   		 [[NSNotificationCenter defaultCenter] removeObserver:self];
	}
###

8.didSelectRowAtIndexPath ------>选中cell
-----------------------------------
###
	- (void)tableView:(UITableView *)tableView didSelectRowAtIndexPath:(NSIndexPath *)indexPath
	{
		[tableView deselectRowAtIndexPath:indexPath animated:NO];
    
		____[code]____
	}
###



代码块定义
=====

1.add by ------>添加作者信息
-----------------------------------
###
    //add by ____[author]____, begin
    //reason:____[reason]____
    //date:____[yyyy]____-____[mm]____-____[dd]____
    
    ____[code]____
    
    //add end
###

2.apMonitorPointManager	------>添加埋点
-----------------------------------
###
	[[APMonitorPointManager sharedInstance] addLogsAndKeys:kActionID_____[key]____, kActionID, 
			____[业务ID]____, kBizID, ____[埋点ID]____, kActionSeed,
			____[当前视图]____,kCurrentViewID, ____[上一个视图]____,kLastViewID,
			____[(NSString *), ...]____, nil];
###

3.NSDocumentDirectory或者documentDirectory ------>获取document路径
-----------------------------------
###
    NSArray *paths = NSSearchPathForDirectoriesInDomains(NSDocumentDirectory,NSUserDomainMask, YES);
    NSString *documentDirectory = paths.firstObject;
###

4.if ------>if格式
-----------------------------------
###
    if (____[condition]____)
    {
        ____[code]____
    }
###

5.elseif ------>else if格式
-----------------------------------
###
    else if (____[condition]____)
    {
        ____[code]____
    }
###

6.else ------>else格式
-----------------------------------
###
    else
    {
        ____[code]____
    }
###

7.disAsyncMain或者dispatch_async_main或者asyncDispatchMain ------>异步dispatch到主线程
-----------------------------------
###
	dispatch_async(dispatch_get_main_queue(), ^{
                ____[code]____
            });
###

8.disAsyncGlobal或者dispatch_async_global或者asyncDispatchGlobal ------>异步dispatch到global
-----------------------------------
###
	dispatch_async(dispatch_get_global_queue(DISPATCH_QUEUE_PRIORITY_DEFAULT, 0), ^{
                ____[code]____
            });
###

9.switch ------>switch格式
-----------------------------------
### 
    switch (____[expression]____)
    {
        case ____[constant]____:
        {
            ____[code]____
            break;
        }
        default:
        {
            ____[code]____
            break;
        }
    }
###

10.case ------>case格式
-----------------------------------
###
        case ____[constant]____:
        {
            ____[code]____
            
            break;
        }
###

11.@synchronized ------>同步块
-----------------------------------
###
    @synchronized(self)
    {
        ____[code]____
    }
###

12.test ------>添加test测试代码块
-----------------------------------
###
        //test
    #ifdef DEBUG
        ____[code]____
        return ____[expression]____
    #endif
        //test
###

13.forSubViews ------>枚举subViews格式
-----------------------------------
###
    for (UIView *subView in [____[self.view]____ subviews])
    {
        NSLog(@"subView = %@", subView);
        ____[code]____
    }
###

14.exitCurrentApp或者exitApp或者appExit ------>退出当前app
-----------------------------------
###
    [DTContextGet().currentApplication exitAnimated:____[YES]____];
###


15.pragmaAll ------>代码职责分块
-----------------------------------
###
    #pragma mark - private



    #pragma mark ______doing


    #pragma mark ______clicked


    #pragma mark ______create



    #pragma mark ______notif



    #pragma mark - Delegates



    #pragma mark - public
###

16.pragmaMain ------>分块主分割线
-----------------------------------
###
    #pragma mark - ____[mainMark]____
###

17.pragmaSection ------>分块次分割线
-----------------------------------
###
    #pragma mark __________[section]____
###

18.modifyBy ------>添加修改作者
-----------------------------------
###
    //modify by ____[author]____, begin
    //reason:____[reason]____
    //date:____[yyyy]____-____[mm]____-____[dd]____
    
    ____[code]____
    
    //modify end
###

19.nsNotificationCenterAddObserverName或者notifAddObserverName ------>根据name，添加监听消息
-----------------------------------
###
    [[NSNotificationCenter defaultCenter] removeObserver:____[self]____
                                                    name:____[(NSString *)]____
                                                  object:____[nil]____];
    [[NSNotificationCenter defaultCenter] addObserver:____[self]____
                                             selector:____[(SEL)]____
                                                 name:____[(NSString *)]____
                                               object:____[nil]____];
###

20.nsNotificationCenterRemoveObserverName或者notifRemoveObserverName ------>根据name，移除监听消息
-----------------------------------
###
    [[NSNotificationCenter defaultCenter] removeObserver:____[self]____
                                                    name:____[(NSString *)]____
                                                  object:____[nil]____];
###

21.nsNotificationCenterRemoveObserver或者notifRemoveObserver ------>取消监听消息
###
    [[NSNotificationCenter defaultCenter] removeObserver:____[self]____];
###

22.performBackground或者backgroundPerform ------>后台线程执行该函数
-----------------------------------
###
    [self performSelectorInBackground:____[(SEL)]____ withObject:____[nil]____];
###

23.performMain或者mainPerform ------>主线程执行该函数
-----------------------------------
###
    [self performSelectorOnMainThread:____[(SEL)]____ withObject:____[nil]____ waitUntilDone:____[(BOOL)]____];
###

24.performDelay或者delayPerform ------>延迟执行该函数
-----------------------------------
###
    [self performSelector:____[(SEL)]____ withObject:____[nil]____ afterDelay:____[(NSTimeInterval)]____];
###

25.popViewController ------>pop当前vc
-----------------------------------
###
    [self.navigationController popViewControllerAnimated:____[YES]____];
###

26.popViewController ------>pop当前vc
-----------------------------------
###

27.popToViewController ------>pop到vc
-----------------------------------
###
    [self.navigationController popToViewController:____[vc]____ animated:____[YES]____];
###

28.popToRootViewController ------>pop到根vc
-----------------------------------
###
    [self.navigationController popToRootViewControllerAnimated:____[YES]____];
###

29.postNotificationName ------>发送name消息
-----------------------------------
###
    [[NSNotificationCenter defaultCenter] postNotificationName:____[name]____ object:____[nil]____];
###

30.pushViewController ------>push一个vc
-----------------------------------
###
    [self.navigationController pushViewController:____[vc]____ animated:____[YES]____];
###

31.animationSimple ------>简单动画
-----------------------------------
###
    [UIView animateWithDuration:0.3f
                     animations:^{
                         ____[code]____
                     } completion:^(BOOL finished) {
                         
                     }];
###

32.startApp或者appStart ------>启动一个app
-----------------------------------
###
    [DTContextGet() startApplication:____[appId]____ params:____[params]____ animated:____[YES]____];
###


tools
