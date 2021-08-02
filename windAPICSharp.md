1. Wind终端->我的->插件修复->修复C#接口
2. 引用WAPIWrapperCSharp.dll
3. using WAPIWrapperCSharp;
4. ```c#
    WindAPI w = new WindAPI();
    w.start();
    w.isconnected();
    WindData wd = ...;
    wd.GetDataLength();
    wd.GetCodeLength();
    wd.GetFieldLength();
    type data = (type)wd.getDataByFunc(string funcName, false);
    w.stop();
