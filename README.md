# XpressEngine/Rhymix Coding Standard

## 개요
이 코딩스탠다드는 XE 및 Rhymix(이하 RXE)에서 코딩할 경우 최적의 코딩스탠다드를 소개합니다.

이 코딩스탠다드를 굳이 따르지 않아도 되며 각자의 코딩규칙대로 코딩하시면 됩니다.

###### 기본 설정
1. PHP, HTML, XML, CSS, JS등 모든 텍스트 파일의 문자색은 BOM이 없는 UTF-8으로 한다.
2. 줄바꿈은 유닉스 방식(LF)을 따른다.
3. 들여쓴 줄들의 사이의 빈줄도 들여쓴다.
4. PHP코드로 이루어진 파일의 경우 맨끝 ?> PHP 닫는 코드를 넣지 않는다.
5. 지역 변수 및 함수 매개 변수에는 낙타케이싱 기법으로 이름을 정한다.
	* `public function getMemberInfoByMemberSrl($member_srl)`
	* `public $memberPrivateData = null;`
6. class 및 function 선언과 if, for, foreach, while 등의 중괄호는 다음 줄에 쓴다.
```php
public function bar($foo)
{
	// 내용
}
```
7. 조건문 혹은 순환문 내에 한 줄의 코드가 있더라도 항상 중괄호를 열고 닫아야 한다. 단, 클로저의 경우 같은 줄에 중갈호를 사용할 수 있으나 열고 닫히는 중갈호 사이에 항상 공백이 존재해야 한다.
```php
if($variables)
{
	$variables = $memberVariable;
}
```
8. 함수 호출시 함수명과 갈호사이, 괄호의 인자사이에 공백을 두지 않는다. 인자를 구분하는 쉼표의 뒤쪽에만 한 칸의 공백을 둔다.
```php
public static function someMethod($someParameters, $secParameters)
```
9. if, for, foreach, while 등의 키워드 뒤에는 한 칸의 공백을 둘 수 있으며 ==, !=, > 등의 연산자는 앞뒤에 한 칸씩 공백을 반드시 둔다. if, for, foreach, while 등의 키워드 뒤에 한 칸의 공백을 두지 않아도 됩니다.
```php
if ($someVariable === $someParameters)
```
10. PHP에서 여러줄에 걸쳐 배열을 선언할 경우, 마지막 구성요소 뒤에 쉼표를 남긴다. 단 자바스크립트 및 Json에서는 마지막 쉼표를 반드시 삭제해야 한다. 이외 다른 언어에서는 마지막에 쉼표를 반드시 삭제한다.
```php
$memberSrls = array(
	'309',
	'801',
	'515',
);
```
11. switch문에는 항상 기본값이 있어야 한다.
```php
switch ($expr)
{
	case 0:
		echo 'First case, with a break';
		break;
	case 1:
		echo 'Second case, which falls through';
		// no break
	case 2:
	case 3:
	case 4:
		echo 'Third case, return instead of break';
		return;
	default:
		echo 'Default case';
		break;
}
```
12. 주석은 관련 코드 윗줄에 써야한다.
13. 모든 클래스와 함수에는 `/**` 으로 시작하는 PHPDoc방식의 주석을 붙일 수 있도록 한다.
14. 주석은 불필요한 주석을 적지 않는다. 동작 마다 모두 주석을 달 필요가 없다. 코드로 쉽게 동작을 이해할 수 있는 경우 작동에 대한 주석을 적지 않고 정말로 코드가 동작이 이해하기 어려운 경우에 작성합니다. TODO, 및 채크해야할 부분은 항상 작성을 해두도록 합니다.
15. 특정 IDE에서 자체적인 IDE기능을 위한 클래스 변수에 주석을 일시적으로 허용한다.
```php
/** @var $oMemberModel memberModel */
$oMemberModel = getModel(‘member’);
```
16. 문자열, 혹은 정수간의 비교시 `==`보단 `===`을 사용하도록 합니다.
17. array를 사용시 `[1, 2, 3]`과 같이 사용할 수 있다. 다만 가독성을 해칠 우려가 있는 부분에서는 항상 array() 함수를 사용하도록 한다.
18. 전역 상수를 참조시 `\RX_BASE_DIR`와 같이 `\`를 앞에 붙여 추후 다른 네임스페이스로 코드를 이동 또는 복사하더라도 문제가 생기지 않도록 한다.
19. 여기서 언급되지 않은 모든 내용은 [PSR-1](https://www.php-fig.org/psr/psr-1/)과 [PSR-12](https://www.php-fig.org/psr/psr-12/)를 따르도록 한다.
20. 들여쓴 줄들 사이의 빈 줄들도 들여빈줄로 둘 것.