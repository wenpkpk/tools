tools
=====

Xcode代码片段共享
使用：
    git下载完，放在系统~/Library/Developer/Xcode/UserData/CodeSnippets

1.add by	-添加作者
###
    //add by left***author***right, begin
    //reason:left***reason***right
    //date:left***yyyy***right-left***mm***right-left***dd***right
    
    left***statements***right
    
    //add end
###

2.apMonitorPointManager	—-埋点
###
	[[APMonitorPointManager sharedInstance] addLogsAndKeys:kActionID_left***key***right, kActionID, left***业务ID***right, kBizID, left***埋点ID***right, kActionSeed,   left***当前视图***right,kCurrentViewID, left***上一个视图***right,kLastViewID,left***(NSString *), ...***right, nil];
###


3.cellForRowAtIndexPath	—-cell
###
	- (UITableViewCell *)tableView:(UITableView *)tableView cellForRowAtIndexPath:(NSIndexPath *)indexPath
	{
   	 left***UITableViewCell***right *cell = [tableView dequeueReusableCellWithIdentifier:left***@"cell"***right];
    
   	 if (nil == cell)
   	 {
      		  cell = [[UITableViewCell alloc]initWithStyle:UITableViewCellStyleDefault reuseIdentifier:left***@"cell"***right];
  	  }
    
    left***statements***right
    
    return cell;
	}
###

4.clicked
###
	- (void)left***btn***rightClicked:(id)sender
	{
    
	}
###

5.myCell
###
	static NSString *cellIdentifier = left***@"cellIdentifier"***right;
	UITableViewCell *cell = [tableView dequeueReusableCellWithIdentifier:cellIdentifier];

	if (!cell)
	{
    		cell = [[UITableViewCell alloc] initWithStyle:UITableViewCellStyleDefault reuseIdentifier:cellIdentifier];
	}
###

6.dealloc
###
	-(void)dealloc
	{
   		 [NSObject cancelPreviousPerformRequestsWithTarget:self];
   		 [[NSNotificationCenter defaultCenter] removeObserver:self];
	}
###

7.id
###
	idleft***protocol***right left***delegate***right;
###

8.didSelectRowAtIndexPath
###
	- (void)tableView:(UITableView *)tableView didSelectRowAtIndexPath:(NSIndexPath *)indexPath
	{
    		[tableView deselectRowAtIndexPath:indexPath animated:NO];
    
   	 	left***statements***right
	}
###

9.disAsyncMain或者dispatch_async_main
###
	dispatch_async(dispatch_get_main_queue(), ^{
                left***code***right
            });
###

10.disAsyncGlobal或者dispatch_async_global
###
	dispatch_async(dispatch_get_global_queue(DISPATCH_QUEUE_PRIORITY_DEFAULT, 0), ^{
                left***code***right
            });
###


tools
