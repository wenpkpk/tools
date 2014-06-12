tools
=====
\#\>
Xcode代码片段共享
使用：
    git下载完，放在系统~/Library/Developer/Xcode/UserData/CodeSnippets

1.add by	-添加作者
###
    //add by \<\#author\#\>, begin
    //reason:\<\#reason\#\>
    //date:\<\#yyyy\#\>-\<\#mm\#\>-\<\#dd\#\>
    
    \<\#statements\#\>
    
    //add end
###

2.apMonitorPointManager	—-埋点
###
[[APMonitorPointManager sharedInstance] addLogsAndKeys:kActionID_\<\#key\#\>, kActionID, \<\#业务ID\#\>, kBizID, \<\#埋点ID\#\>, kActionSeed,   \<\#当前视图\#\>,kCurrentViewID, \<\#上一个视图\#\>,kLastViewID,\<\#(NSString *), ...\#\>, nil];
###


3.cellForRowAtIndexPath	—-cell
###
- (UITableViewCell *)tableView:(UITableView *)tableView cellForRowAtIndexPath:(NSIndexPath *)indexPath
{
    \<\#UITableViewCell\#\> *cell = [tableView dequeueReusableCellWithIdentifier:\<\#@"cell"\#\>];
    
    if (nil == cell)
    {
        cell = [[UITableViewCell alloc]initWithStyle:UITableViewCellStyleDefault reuseIdentifier:\<\#@"cell"\#\>];
    }
    
    \<\#statements\#\>
    
    return cell;
}
###

4.clicked
###
- (void)\<\#btn\#\>Clicked:(id)sender
{
    
}
###

5. myCell
###
static NSString *cellIdentifier = \<\#@"cellIdentifier"\#\>;
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
id\<\#protocol\#\> \<\#delegate\#\>;
###

8. didSelectRowAtIndexPath
###
- (void)tableView:(UITableView *)tableView didSelectRowAtIndexPath:(NSIndexPath *)indexPath
{
    [tableView deselectRowAtIndexPath:indexPath animated:NO];
    
    \<\#statements\#\>
}
###

9.disAsyncMain或者dispatch_async_main
###
dispatch_async(dispatch_get_main_queue(), ^{
                \<\#code\#\>
            });
###

10.disAsyncGlobal或者dispatch_async_global
###
dispatch_async(dispatch_get_global_queue(DISPATCH_QUEUE_PRIORITY_DEFAULT, 0), ^{
                \<\#code\#\>
            });
###


tools
