若需增加刷题章节及题目，需要新增章节的数据，并更新章节元数据和分组配置。

需要修改的代码位置
1. 新增章节数据（约第 800-900 行）
在 CHAPTER_12 数组后面，比如添加第13、14、15章的数据：

javascript
// ================================================================
// ★★★ 第13节 新增课后习题（3题）★★★
// ================================================================
const CHAPTER_13 = [
    {
        id: 101,  // 注意ID不能重复
        chapter: 13,
        group: 'theory',
        text: '你的题目内容1',
        options: ['A、选项A', 'B、选项B', 'C、选项C', 'D、选项D'],
        answer: 'A',
        explanation: '解析内容1'
    },
    {
        id: 102,
        chapter: 13,
        group: 'theory',
        text: '你的题目内容2',
        options: ['A、选项A', 'B、选项B', 'C、选项C', 'D、选项D'],
        answer: 'B',
        explanation: '解析内容2'
    },
    {
        id: 103,
        chapter: 13,
        group: 'theory',
        text: '你的题目内容3',
        options: ['A、选项A', 'B、选项B', 'C、选项C', 'D、选项D'],
        answer: 'C',
        explanation: '解析内容3'
    }
];

// ================================================================
// ★★★ 第14节 历年真题（3题）★★★
// ================================================================
const CHAPTER_14 = [
    {
        id: 201,
        chapter: 14,
        group: 'exam',
        text: '你的真题内容1',
        options: ['A、选项A', 'B、选项B', 'C、选项C', 'D、选项D'],
        answer: 'A',
        explanation: '解析内容1'
    },
    {
        id: 202,
        chapter: 14,
        group: 'exam',
        text: '你的真题内容2',
        options: ['A、选项A', 'B、选项B', 'C、选项C', 'D、选项D'],
        answer: 'B',
        explanation: '解析内容2'
    },
    {
        id: 203,
        chapter: 14,
        group: 'exam',
        text: '你的真题内容3',
        options: ['A、选项A', 'B、选项B', 'C、选项C', 'D、选项D'],
        answer: 'C',
        explanation: '解析内容3'
    }
];

// ================================================================
// ★★★ 第15节 历年真题（3题）★★★
// ================================================================
const CHAPTER_15 = [
    {
        id: 301,
        chapter: 15,
        group: 'exam',
        text: '你的真题内容1',
        options: ['A、选项A', 'B、选项B', 'C、选项C', 'D、选项D'],
        answer: 'A',
        explanation: '解析内容1'
    },
    {
        id: 302,
        chapter: 15,
        group: 'exam',
        text: '你的真题内容2',
        options: ['A、选项A', 'B、选项B', 'C、选项C', 'D、选项D'],
        answer: 'B',
        explanation: '解析内容2'
    },
    {
        id: 303,
        chapter: 15,
        group: 'exam',
        text: '你的真题内容3',
        options: ['A、选项A', 'B、选项B', 'C、选项C', 'D、选项D'],
        answer: 'C',
        explanation: '解析内容3'
    }
];
2. 更新章节元数据（约第 900-920 行）
在 CHAPTER_META 对象中添加新章节：

javascript
const CHAPTER_META = {
    12: { name: '第12节 信息处理基础', group: 'theory', icon: '📊', count: 27, preview: 0 },
    13: { name: '第13节 新增课后习题', group: 'theory', icon: '📖', count: 3, preview: 0 },
    14: { name: '第14节 历年真题（一）', group: 'exam', icon: '📝', count: 3, preview: 0 },
    15: { name: '第15节 历年真题（二）', group: 'exam', icon: '📝', count: 3, preview: 0 }
};
3. 更新分组配置（约第 920-930 行）
在 GROUP_CHAPTERS 中添加新章节ID：

javascript
const GROUP_CHAPTERS = {
    theory: [12, 13],      // 课后习题组：添加第13章
    exam: [14, 15]         // 历年真题组：添加第14、15章
};
4. 汇总所有章节数据（约第 930-940 行）
在 ALL_CHAPTER_DATA 中添加新章节：

javascript
const ALL_CHAPTER_DATA = {
    12: CHAPTER_12,
    13: CHAPTER_13,
    14: CHAPTER_14,
    15: CHAPTER_15
};
5. 更新章节徽章数量（约第 30-40 行，HTML部分）
在 group-tabs 中更新徽章数字：

html
<div class="group-tabs" id="groupTabs">
    <button class="group-tab active" data-group="theory">📖 课后习题 <span class="badge">2节</span></button>
    <button class="group-tab" data-group="exam">📝 历年真题 <span class="badge">2节</span></button>
</div>
