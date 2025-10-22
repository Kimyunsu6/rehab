import java.util.Scanner; // Scanner 사용을 위해 import

public class Main { // 클래스 이름은 Main 또는 문제에서 지정한 이름으로
    public static void main(String[] args) {
        // 1. Scanner 객체 생성 (키보드 입력을 위함)
        Scanner sc = new Scanner(System.in);

        // 2. 입력 받기 (예시)
        
        // 정수 한 개 입력
        int n = sc.nextInt(); [cite: 1829]

        // 실수 한 개 입력
        double d = sc.nextDouble(); [cite: 1837]

        // 단어 한 개 입력 (공백 기준)
        String s1 = sc.next(); [cite: 1837]
        
        // [중요!] nextInt() 등 다음에 nextLine()을 쓸 때
        // sc.nextLine(); // 이전에 입력된 줄바꿈(엔터) 문자를 비워줍니다. [cite: 1941]

        // 한 줄 전체 입력 (공백 포함)
        String line = sc.nextLine(); [cite: 1830]
        
        // 3. 알고리즘 풀이 (로직 구현)
        // ... (이곳에 로직을 구현합니다) ...

        // 4. 출력
        
        // 기본 줄바꿈 출력
        System.out.println("출력할 값: " + n);

        // 줄바꿈 없는 출력
        System.out.print("이어서 출력됩니다.");

        // 형식 지정 출력 (printf) [cite: 1744]
        // %d (정수), %f (실수), %s (문자열), %c (문자), \n (줄바꿈) [cite: 1753]
        System.out.printf("정수: %d, 실수: %.2f, 문자열: %s\n", n, d, s1);

        // 5. Scanner 닫기 (필수는 아니지만 좋은 습관)
        sc.close();
    }
}


// 1. 문자열(String) -> 정수(int) [cite: 1953, 1955]
String strNum = "123";
int num = Integer.parseInt(strNum); [cite: 1327]

// 2. 문자열(String) -> 실수(double) [cite: 1953]
String strDouble = "3.14";
double dNum = Double.parseDouble(strDouble);

// 3. 숫자 -> 문자열(String)
int numToConvert = 456;
String strConverted = String.valueOf(numToConvert); // 방법 1
String strConverted2 = Integer.toString(numToConvert); // 방법 2 [cite: 1327]
String strConverted3 = numToConvert + ""; // (간단한 방법)

// 4. 강제 형 변환 (Casting) [cite: 1651, 1657]
double myDouble = 9.78;
int myInt = (int) myDouble; // myInt는 9가 됨 (소수점 버림) [cite: 1668]

// 5. 정수 나눗셈 시 실수 결과 얻기 [cite: 2004]
int a = 5;
int b = 2;
// double result = a / b; // 2.0 (정수 나눗셈 후 형변환)
double result = (double) a / b; // 2.5 (실수 나눗셈)


// 1. if-else if-else [cite: 3421]
int score = 85;
if (score >= 90) {
    System.out.println("A");
} else if (score >= 80) { // 80 <= score < 90
    System.out.println("B");
} else { // score < 80
    System.out.println("C");
}

// 2. 논리 연산자 (&&, ||) [cite: 3366, 3368]
int gpa = 3;
int incomeLevel = 6;
// AND (&&): 둘 다 true여야 true
if (gpa >= 3.5 && incomeLevel <= 5) { [cite: 3509, 3533]
    System.out.println("장학생 후보");
}
// OR (||): 둘 중 하나만 true여도 true
if (gpa < 2.0 || incomeLevel > 8) {
    System.out.println("학사 경고");
}

// 3. 문자열 비교 (== 사용 금지!) [cite: 3329]
String s1 = "hello";
String s2 = sc.next(); // "hello"를 입력했다고 가정
// if (s1 == s2) { ... } // (X) 주소값 비교 [cite: 3351]
if (s1.equals(s2)) { // (O) 내용 비교 [cite: 3355]
    System.out.println("두 문자열이 같습니다.");
}

// 4. switch-case (int, char, String, enum 사용 가능) [cite: 4025, 4111]
String zone = "prime";
switch (zone) { [cite: 4111]
    case "prime": [cite: 4116]
        System.out.println("11000원");
        break; [cite: 4118]
    case "standard":
        System.out.println("10000원");
        break;
    default: [cite: 4034]
        System.out.println("잘못 입력");
        break;
}

// 5. 삼항 연산자 [cite: 3488]
int score = 70;
String status = (score >= 60) ? "pass" : "fail"; [cite: 3496]

// 1. for 루프 (정해진 횟수) [cite: 3681]
// 1부터 10까지 합계 [cite: 3691]
int sum = 0;
for (int i = 1; i <= 10; i++) {
    sum += i; // sum = sum + i; [cite: 3693, 2062]
}
System.out.println("합계: " + sum);

// 2. while 루프 (조건 만족 시) [cite: 3605]
int n = 10;
while (n > 0) {
    System.out.println(n);
    n--; // n = n - 1; (종료 조건에 다가가야 함) [cite: 2043]
}

// 3. do-while 루프 (최소 1번 실행) [cite: 3647, 3649]
int input;
do {
    System.out.print("숫자 입력 (0이면 종료): ");
    input = sc.nextInt();
} while (input != 0);

// 4. for-each 루프 (배열/컬렉션 순회) [cite: 3828]
int[] scores = { 90, 80, 70 };
for (int score : scores) {
    System.out.println(score);
}

// 5. break / continue
for (int i = 0; i < 10; i++) {
    if (i == 3) {
        continue; // 3일 때만 건너뛰고 다음 반복(i=4)으로 [cite: 3748]
    }
    if (i == 7) {
        break; // 7일 때 반복문 즉시 탈출 [cite: 3729]
    }
    System.out.println(i); // 0, 1, 2, 4, 5, 6 출력
}


// 1. 배열 선언 및 초기화 (크기 고정)

// 방법 A: new 키워드로 공간 할당 (0, 0.0, false, null로 자동 초기화) [cite: 2204, 2210]
int[] arr1 = new int[5]; // 5칸짜리 int 배열
arr1[0] = 100;
arr1[1] = 200;

// 방법 B: 리터럴로 즉시 초기화 [cite: 2198, 2206]
String[] days = { "Mon", "Tue", "Wed", "Thu", "Fri" };

// 2. 배열 순회 (for 루프 사용)
// .length: 배열의 길이 (속성, 메소드 아님!) [cite: 2230]
for (int i = 0; i < arr1.length; i++) { [cite: 3697]
    System.out.println(arr1[i]);
}

// 3. 클래스(객체) 배열
// (Student 클래스가 아래 7번에 정의되어 있다고 가정) [cite: 1215]
Student[] studentArray = new Student[3]; // [null, null, null] 상태

// [중요!] 배열 공간만 만들고 객체를 생성하지 않으면 NullPointerException 발생
studentArray[0] = new Student("홍길동", 20210001); [cite: 1225, 1291]
studentArray[1] = new Student("김철수", 20210002);
studentArray[2] = new Student("이영희", 20210003);

// 클래스 배열 순회
for (Student s : studentArray) {
    System.out.println(s.getName()); // 객체 메소드 호출
}

String s = "Hello, Java";

// 1. 기본 정보 [cite: 714]
int len = s.length(); // 11
char ch = s.charAt(0); // 'H'

// 2. 검색 및 비교 [cite: 714, 719]
int idx = s.indexOf("Java"); // 7 (못 찾으면 -1)
boolean contains = s.contains("llo"); // true
boolean ends = s.endsWith(".java"); // false
boolean equals = s.equals("hello, java"); // false (대소문자 구분)
boolean equalsIc = s.equalsIgnoreCase("hello, java"); // true

// 3. 자르기 및 분리 [cite: 719, 3921]
String sub1 = s.substring(7); // "Java" (7번 인덱스부터 끝까지)
String sub2 = s.substring(0, 5); // "Hello" (0부터 4까지, 5는 불포함)
String[] parts = s.split(","); // ["Hello", " Java"]

// 4. (참고) 문자열이 "숫자 1 2 3" 처럼 공백으로 구분될 때
String line = "10 20 30";
String[] numbers = line.split(" "); // 공백 기준 분리
int num1 = Integer.parseInt(numbers[0]); // 10

// 5. StringBuilder (문자열을 반복문 안에서 합칠 때) [cite: 754]
StringBuilder sb = new StringBuilder(); [cite: 760]
for (int i = 0; i < 5; i++) {
    sb.append(i); // "01234" [cite: 761]
    sb.append(" "); // "0 1 2 3 4 "
}
String result = sb.toString(); // 최종 문자열로 변환


// 1. 클래스 정의
public class Student {
    
    // A. 필드 (멤버 변수): 데이터. private으로 캡슐화 [cite: 845, 905]
    private String name;
    private int studentId;
    private String major;

    // B. 생성자: 객체를 'new' 할 때 호출되는 메소드. 필드 초기화 담당 [cite: 1002, 1003]
    public Student(String name, int studentId) {
        this.name = name; // 'this'는 객체 자신을 의미 [cite: 1078, 1084]
        this.studentId = studentId;
        this.major = "미정"; // 기본값 설정
    }

    // 생성자 오버로딩 (Overloading) [cite: 1043]
    public Student(String name, int studentId, String major) {
        this.name = name;
        this.studentId = studentId;
        this.major = major;
    }

    // C. 메소드 (멤버 함수): 기능
    
    // Getter (필드 값 읽기) [cite: 1319]
    public String getName() {
        return this.name;
    }

    // Setter (필드 값 설정) [cite: 1319]
    public void setMajor(String major) {
        this.major = major;
    }
    
    // 일반 메소드
    public void printInfo() {
        System.out.printf("이름: %s, 학번: %d, 전공: %s\n", 
            this.name, this.studentId, this.major);
    }
}

// 2. 객체 생성 및 사용 (main 메소드 등 다른 곳에서)
// Student s1 = new Student("김자바", 2023001, "컴퓨터공학"); [cite: 226]
// s1.printInfo(); // 메소드 호출 [cite: 227]
// s1.setMajor("AI학과"); // Setter로 값 변경
// System.out.println(s1.getName()); // Getter로 값 읽기



public class MyMethods {

    // 1. 일반 메소드 (클래스 내부) [cite: 2372]
    // 두 정수의 합을 반환하는 함수
    public int add(int a, int b) { [cite: 55, 2404]
        return a + b; // 'return'으로 결과 반환 [cite: 56, 2407]
    }

    // 2. 메소드 오버로딩 (이름은 같고, 매개변수 타입/개수가 다름) [cite: 2897, 2907]
    public double add(double a, double b) { [cite: 2982]
        return a + b;
    }

    // 3. 재귀 함수 (스스로를 호출하는 함수) [cite: 3004]
    // 팩토리얼 예시: n! = n * (n-1)!
    public long factorial(int n) { [cite: 3035]
        // A. 종료 조건 (필수!) [cite: 3141]
        if (n == 0 || n == 1) { [cite: 3036]
            return 1;
        }
        // B. 재귀 호출
        return n * factorial(n - 1); [cite: 3036]
    }
    
    // 사용 예시
    // MyMethods calculator = new MyMethods();
    // int sum = calculator.add(5, 3);
    // long fact = calculator.factorial(5); // 120
}

// 1. 기본 Enum 선언 [cite: 4151, 4154]
enum TrafficLight {
    RED, AMBER, GREEN; [cite: 4376]
}

// 2. Enum 사용
TrafficLight light = TrafficLight.RED;

// 3. Enum과 switch-case (매우 유용) [cite: 4212]
switch (light) {
    case RED:
        System.out.println("정지");
        break;
    case AMBER:
        System.out.println("주의");
        break;
    case GREEN:
        System.out.println("진행");
        break;
}

// 4. Enum 순회 (values() 메소드) [cite: 4218]
for (TrafficLight tl : TrafficLight.values()) {
    System.out.println(tl); // RED, AMBER, GREEN 순서대로 출력
}

// 5. 값(필드)과 메소드를 가진 Enum [cite: 4232, 4375]
enum Day {
    SUNDAY(0), 
    MONDAY(1), 
    TUESDAY(2);

    private final int dayValue;

    // 생성자 (private이 기본)
    Day(int dayValue) { [cite: 4253, 4378]
        this.dayValue = dayValue;
    }

    // 메소드
    public int getDayValue() { [cite: 4253, 4379]
        return this.dayValue;
    }
}

// 사용 예:
// Day today = Day.MONDAY;
// System.out.println(today.getDayValue()); // 1 출력

// [활용 예: 스마트폰 메뉴]
Scanner sc = new Scanner(System.in);
boolean isRunning = true; // true인 동안 계속 실행

while (isRunning) {
    System.out.println("1. 연락처 추가 | 2. 연락처 검색 | 3. 종료");
    System.out.print("메뉴 선택: ");
    int menu = sc.nextInt();

    switch (menu) {
        case 1:
            // ... (연락처 추가 로직) ...
            System.out.println("연락처를 추가합니다.");
            break;
        case 2:
            // ... (연락처 검색 로직) ...
            System.out.println("연락처를 검색합니다.");
            break;
        case 3:
            isRunning = false; // while 루프 종료
            System.out.println("프로그램을 종료합니다.");
            break;
        default:
            System.out.println("잘못된 입력입니다.");
            break;
    }
}
