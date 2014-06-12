tools
=====

Xcode代码片段共享
使用：
    git下载完，放在系统~/Library/Developer/Xcode/UserData/CodeSnippets


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

4.clicked ------>按钮事件
-----------------------------------
###
	- (void)____[btn]____Clicked:(id)sender
	{
    
	}
###

5.myCell ------>创建cell
-----------------------------------
###
	static NSString *cellIdentifier = ____[@"cellIdentifier"]____;
	UITableViewCell *cell = [tableView dequeueReusableCellWithIdentifier:cellIdentifier];

	if (!cell)
	{
    		cell = [[UITableViewCell alloc] initWithStyle:UITableViewCellStyleDefault reuseIdentifier:cellIdentifier];
	}
###

6.dealloc ------>取消监听的dealloc
-----------------------------------
###
	-(void)dealloc
	{
   		 [NSObject cancelPreviousPerformRequestsWithTarget:self];
   		 [[NSNotificationCenter defaultCenter] removeObserver:self];
	}
###

7.id ------>声明delegate
-----------------------------------
###
	id____[protocol]____ ____[delegate]____;
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

9.disAsyncMain或者dispatch_async_main ------>异步dispatch到主线程
-----------------------------------
###
	dispatch_async(dispatch_get_main_queue(), ^{
                ____[code]____
            });
###

10.disAsyncGlobal或者dispatch_async_global ------>异步dispatch到global
-----------------------------------
###
	dispatch_async(dispatch_get_global_queue(DISPATCH_QUEUE_PRIORITY_DEFAULT, 0), ^{
                ____[code]____
            });
###


tools
