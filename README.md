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



tools
