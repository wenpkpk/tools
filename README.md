tools
=====

Xcode代码片段共享
使用：
    git下载完，放在系统~/Library/Developer/Xcode/UserData/CodeSnippets


1.add by ------>添加作者信息
-----------------------------------
###
    //add by <b>author</b>, begin
    //reason:<b>reason</b>
    //date:<b>yyyy</b>-<b>mm</b>-<b>dd</b>
    
    <b>statements</b>
    
    //add end
###

2.apMonitorPointManager	------>添加埋点
-----------------------------------
###
	[[APMonitorPointManager sharedInstance] addLogsAndKeys:kActionID_<b>key</b>, kActionID, <b>业务ID</b>, kBizID, <b>埋点ID</b>, kActionSeed,   <b>当前视图</b>,kCurrentViewID, <b>上一个视图</b>,kLastViewID,<b>(NSString *), ...</b>, nil];
###


3.cellForRowAtIndexPath	------>cell
-----------------------------------
###
	- (UITableViewCell *)tableView:(UITableView *)tableView cellForRowAtIndexPath:(NSIndexPath *)indexPath
	{
   	 <b>UITableViewCell</b> *cell = [tableView dequeueReusableCellWithIdentifier:<b>@"cell"</b>];
    
   	 if (nil == cell)
   	 {
      		  cell = [[UITableViewCell alloc]initWithStyle:UITableViewCellStyleDefault reuseIdentifier:<b>@"cell"</b>];
  	  }
    
    <b>statements</b>
    
    return cell;
	}
###

4.clicked ------>按钮事件
-----------------------------------
###
	- (void)<b>btn</b>Clicked:(id)sender
	{
    
	}
###

5.myCell ------>创建cell
-----------------------------------
###
	static NSString *cellIdentifier = <b>@"cellIdentifier"</b>;
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
	id<b>protocol</b> <b>delegate</b>;
###

8.didSelectRowAtIndexPath ------>选中cell
-----------------------------------
###
	- (void)tableView:(UITableView *)tableView didSelectRowAtIndexPath:(NSIndexPath *)indexPath
	{
    		[tableView deselectRowAtIndexPath:indexPath animated:NO];
    
   	 	<b>statements</b>
	}
###

9.disAsyncMain或者dispatch_async_main ------>异步dispatch到主线程
-----------------------------------
###
	dispatch_async(dispatch_get_main_queue(), ^{
                <b>code</b>
            });
###

10.disAsyncGlobal或者dispatch_async_global ------>异步dispatch到global
-----------------------------------
###
	dispatch_async(dispatch_get_global_queue(DISPATCH_QUEUE_PRIORITY_DEFAULT, 0), ^{
                <b>code</b>
            });
###


tools
