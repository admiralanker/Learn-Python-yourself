<script src =“ raphael-min.js ”> <
<script src =“ flowchart-latest.js ”> </ script>
您可以解析文本：

<div id =“diagram”> </ div>
<SCRIPT>
  var diagram = flowchart.parse（“代码定义”）;
  diagram.drawSVG（ '图'）;

  //你也可以尝试传递选项：

  diagram.drawSVG（'diagram'，{
                              'x'：0，
                              'y'：0，
                              'line-width'：3，
                              'line-length'：50，
                              'text-margin'：10，
                              'font-size'：14，
                              'font-color'：'black'，
                              'line-color'：'black'，
                              'element-color'：'black'，
                              '填'：'白'，
                              '是 - 文字'：'是'，
                              'no-text'：'不'，
                              'arrow-end'：'block'，
                              '规模'：1，
                              //样式符号类型
                              'symbols'：{
                                '开始'：{
                                  'font-color'：'red'，
                                  'element-color'：'green'，
                                  '填'：'黄'
                                }，
                                '结束'：{
                                  'class'：'end-element'
                                }
                              }，
                              //甚至流动状态支持;-)
                              'flowstate'：{
                                '过去'：{'填充'：'＃CCCCCC'，'font-size'：12}，
                                'current'：{'fill'：'yellow'，'font-color'：'red'，'font-weight'：'bold'}，
                                'future'：{'fill'：'＃FFFF99'}，
                                'request'：{'fill'：'blue'}，
                                '无效'：{'fill'：'＃444444'}，
                                'approved'：{'fill'：'＃58C4A3'，'font-size'：12，'yes-text'：'APPROVED'，'no-text'：'n / a'}，
                                '被拒绝'：{'fill'：'＃C45879'，'font-size'：12，'yes-text'：'n / a'，'no-text'：'REJECTED'}
                              }
                            }）;
</ SCRIPT>

st=>start: Start:>http://www.google.com[blank]
e=>end:>http://www.google.com
op1=>operation: My Operation
sub1=>subroutine: My Subroutine
cond=>condition: Yes
or No?:>http://www.google.com
io=>inputoutput: catch something...
para=>parallel: parallel tasks

st->op1->cond
cond(yes)->io->e
cond(no)->para
para(path1, bottom)->sub1(right)->op1
para(path2, top)->op1