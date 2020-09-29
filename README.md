# lua-module
lua ini reader module.

ini读取工具模块lua版

使用示例：

ini内容范例
[ORG]

Name = buerjia

ID = 1001

Address = ChengDu

[Other]

Build = 1.1.0

-- 包含模块
local IniReader = require('IniReader')

local ini_reader = IniReader:New()

if ini_reader:Open('file.ini') then

    print(ini_reader:GetString('ORG', 'Name')) -- buerjia
    
    print(ini_reader:GetInt('ORG', 'ID')) -- 1001
    
    -- 不存在的key
    print(ini_reader:GetInt('ORG', 'IDDDD')) -- nil
    
    -- 不存在的key
    print(ini_reader:GetString('ORG', 'IDDDD')) -- nil
end

对于不存在的节点总会返回nil
