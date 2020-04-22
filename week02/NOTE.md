# 每周总结可以写在这里

## 1.只能有a，b两种字符，任何顺序组成
'a'
'b'
<Program>:= "a"+ | "b"+
<Program>:= <Program> "a"+ | <Program> "b"+


## 2.定义加法

<Number> = "0" | "1" | "2" | ... | "9"
<DeciamalNumber> = "0" | (("0" | "1" | "2" | ... | "9")+ <Number>*)
<AdditiveExpression> = <DeciamalNumber> | <Expression> "+" <DeciamalNumber>

## 3.四则运算
<PrimaryExpression> = <DeciamalNumber> | "(" <LogicalExpression> ")"  带括号的四则运算

<MultiolicativeExpression> = <DeciamalNumber> | 
    <MultiolicativeExpression> "*" <DeciamalNumber> |
    <MultiolicativeExpression> "/" <DeciamalNumber>

<AdditiveExpression> = <MultiolicativeExpression> | 
    <AdditiveExpression> "+" <MultiolicativeExpression>
    <AdditiveExpression> "-" <MultiolicativeExpression>
 
<LogicalExpression> = <AdditiveExpression> | ˜
    <LogicalExpression> "||" <AdditiveExpression>|
    <LogicalExpression> "&&" <AdditiveExpression>

LR||LL语法解析上边代码


LF u+000A  /n (推荐)
CR u+000D  /r
### atom
InputElement
    WhiteSpace
    LineTerminator
    Comment
    Token
        Punctuator  构成
        IdentifierName  有效信息
            Keywords     
            Identifier  
            Future reserved Keywords: enum
        Literal     有效信息
            Number
                IEEE 754
                    Sign(1)
                    Exponent(11)    科学计数法称上去的
                    Fraction(52)    精度部分值
                语法
                0x  16jinzhi
                0o  8jinzhi
                0b  2jinzhi

                eg：Math.abs(0.1+0.2-0.3) <= NumberEPSILON //小于等于 精度
            String
            Boolean
            

