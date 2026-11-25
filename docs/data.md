# 合成资料约定

质量为供应商资料，现场作业许可另行提交；massGrams/grams/readingGrams 均为整数克，累计表跨 restart 不可直接相减；凭证额度独立于实物数量。

| 集合 | 记录数 |
| --- | --- |
| vessels | 2 |
| batches | 2 |
| certificates | 2 |
| orders | 2 |
| windows | 1 |
| meterInputs | 3 |
| actors | 5 |
| sourceChanges | 6 |

同一集合中的 id 唯一，跨集合关联只使用对应字段，不能根据名称合并。日期与完整时间字符串保持各自语义，不用导入时间替换发生时间。字段缺失表示未提供，null 表示明确没有关联；两者均不自动变成已确认状态。actors 是合成角色资料，身份认证和业务接口形式没有现存兼容约束。sourceChanges 是未处理的来源申请或观察，不规定业务执行顺序，也不含预计算结论。

relations.json 中 table/field 指向 target 集合的 id，nullable 表示允许空引用。原始资料可包含尚未复核的状态、待办申请及互相矛盾的主张，应保留提出方和发生时间。文书、意见与决定的效力由有权限的业务人员确认，不能将文件存在本身当作批准。
