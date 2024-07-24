# tasktune
以dify为基础,实现了一个主机任务调度器,支持多任务并行调度,支持任务优先级调度,支持任务依赖调度.

# 特性
- 自定义task模块
- 支持多种沙盒
- 引入主机列表元数,支持对主机打标签,对不同标签的主机进行划分类型及调度

# dify工作流字段解释
### `app` 部分
- **description**: 应用的描述信息，当前为空。
- **icon**: 应用的图标，使用 Unicode 字符表示，当前为 🤖。
- **icon_background**: 图标的背景颜色，当前为 `#FFEAD5`。
- **mode**: 应用的模式，当前为 `workflow`，表示这是一个工作流应用。
- **name**: 应用的名称，当前为 `123`。

### `kind` 和 `version` 部分
- **kind**: 应用的类型，当前为 `app`，表示这是一个应用。
- **version**: 应用的版本号，当前为 `0.1.0`。

### `workflow` 部分
- **features**: 工作流的各种功能配置。
    - **file_upload**: 文件上传功能配置。
        - **image**: 图片上传配置。
            - **enabled**: 是否启用图片上传功能，当前为 `false`。
            - **number_limits**: 图片上传数量限制，当前为 `3`。
            - **transfer_methods**: 图片上传的传输方法，当前为 `local_file` 和 `remote_url`。
    - **opening_statement**: 开场声明，当前为空。
    - **retriever_resource**: 检索资源配置。
        - **enabled**: 是否启用检索资源功能，当前为 `true`。
    - **sensitive_word_avoidance**: 敏感词规避配置。
        - **enabled**: 是否启用敏感词规避功能，当前为 `false`。
    - **speech_to_text**: 语音转文字配置。
        - **enabled**: 是否启用语音转文字功能，当前为 `false`。
    - **suggested_questions**: 建议问题列表，当前为空。
    - **suggested_questions_after_answer**: 回答后建议问题配置。
        - **enabled**: 是否启用回答后建议问题功能，当前为 `false`。
    - **text_to_speech**: 文字转语音配置。
        - **enabled**: 是否启用文字转语音功能，当前为 `false`。
        - **language**: 文字转语音的语言，当前为空。
        - **voice**: 文字转语音的语音，当前为空。

### `graph` 部分
- **edges**: 工作流图中的边（连接）。
    - **id**: 边的唯一标识符。
    - **source**: 边的起始节点 ID。
    - **sourceHandle**: 起始节点的处理类型。
    - **target**: 边的目标节点 ID。
    - **targetHandle**: 目标节点的处理类型。
    - **type**: 边的类型，当前为 `custom`。
    - **zIndex**: 边的层级，当前为 `0`。
    - **data**: 边的数据。
        - **isInIteration**: 是否在迭代中，当前为 `false`。
        - **sourceType**: 起始节点的类型。
        - **targetType**: 目标节点的类型。

- **nodes**: 工作流图中的节点。
    - **id**: 节点的唯一标识符。
    - **position**: 节点的位置。
        - **x**: 节点的 X 坐标。
        - **y**: 节点的 Y 坐标。
    - **positionAbsolute**: 节点的绝对位置。
        - **x**: 节点的绝对 X 坐标。
        - **y**: 节点的绝对 Y 坐标。
    - **selected**: 节点是否被选中，当前为 `false`。
    - **sourcePosition**: 节点的源位置。
    - **targetPosition**: 节点的目标位置。
    - **type**: 节点的类型。
    - **width**: 节点的宽度。
    - **height**: 节点的高度。
    - **data**: 节点的数据。
        - **desc**: 节点的描述信息，当前为空。
        - **selected**: 节点是否被选中，当前为 `false`。
        - **title**: 节点的标题。
        - **type**: 节点的类型。
        - **variables**: 节点的变量。
            - **label**: 变量的标签。
            - **max_length**: 变量的最大长度。
            - **options**: 变量的选项，当前为空。
            - **required**: 变量是否必填。
            - **type**: 变量的类型。
            - **variable**: 变量的名称。
        - **outputs**: 节点的输出。
            - **value_selector**: 输出的值选择器。
            - **variable**: 输出的变量名称。
        - **code**: 节点的代码。
        - **code_language**: 代码的语言。
        - **cases**: 条件分支的案例。
            - **case_id**: 案例的 ID。
            - **conditions**: 案例的条件。
                - **comparison_operator**: 比较运算符。
                - **id**: 条件的 ID。
                - **value**: 条件的值。
                - **varType**: 变量类型。
                - **variable_selector**: 变量选择器。
            - **logical_operator**: 逻辑运算符。
        - **context**: 上下文配置。
            - **enabled**: 是否启用上下文。
            - **variable_selector**: 上下文的变量选择器。
        - **model**: 模型配置。
            - **completion_params**: 完成参数。
                - **temperature**: 温度参数。
            - **mode**: 模型模式。
            - **name**: 模型名称。
            - **provider**: 模型提供者。
        - **prompt_template**: 提示模板。
            - **id**: 提示模板的 ID。
            - **role**: 提示模板的角色。
            - **text**: 提示模板的文本。
        - **vision**: 视觉配置。
            - **configs**: 视觉配置的设置。
                - **detail**: 细节级别。
            - **enabled**: 是否启用视觉功能。

### `viewport` 部分
- **x**: 视口的 X 坐标。
- **y**: 视口的 Y 坐标。
- **zoom**: 视口的缩放级别。

# tasktune提取后的字段解释



