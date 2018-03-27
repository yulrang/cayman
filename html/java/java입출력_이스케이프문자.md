<pre class="brush:java;">public class 표준출력7 {

	public static void main(String[] args) {
		// " " : 문자열을 구분하기 위한 기호
		// ' ' : 문자를 구분하기 위한 기호
		// \ : 이스케이프문자를 구분하기 위한 기호

		System.out.println("\"\"");
		// 큰따옴표 자체를 출력하고 싶을때, 큰따옴표 앞에 \ 붙임
		System.out.println("\'");
		// 작은 따옴표
		System.out.println("\\");
		// 백슬래쉬

		System.out.println();

		System.out.println("\"갤럭시S\"");
		System.out.println("\\50,000");
		System.out.println("\'특가할인\'");

		System.out.println("★,./!@#$%^&amp;*()_+|");
		// 키보드에 없는 특수문자는 한글 자음 + 한자 키

		System.out.println("C:\\Users\\Administrator.SKY-20160902TQY\\Desktop\\");
		System.out.println("C:\\Program Files\\Java\\jdk1.8.0_101");

		System.out.println("http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html");
		System.out.println("https:\\\\eclipse.org\\downloads\\");
	}

}
</pre>
<div><u><br /></u></div><div><u><br /></u></div><div><u>실행결과</u></div><div><br /></div><div><br /></div><div>""</div><div>'</div><div>\</div><div><br /></div><div>"갤럭시S"</div><div>\50,000</div><div>'특가할인'</div><div>★,./!@#$%^&amp;*()_+|</div><div>C:\Users\Administrator.SKY-20160902TQY\Desktop\</div><div>C:\Program Files\Java\jdk1.8.0_101</div><div>http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html</div><div>https:\\eclipse.org\downloads\</div><div><br /></div><p><br /></p>
