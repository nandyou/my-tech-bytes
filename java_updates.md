Sure! Below is a Markdown-formatted summary of Java features from Java 7 to Java 21, suitable for documentation, wikis, or code notes.

⸻

🧠 Java Feature Updates (Java 7 to Java 21)

Covers major language and API changes across key Java versions.

⸻

✅ Java 7 (2011) – Project Coin
	•	Try-with-resources

try (BufferedReader br = new BufferedReader(new FileReader("file.txt"))) {
    System.out.println(br.readLine());
}


	•	Diamond Operator (<>)

List<String> list = new ArrayList<>();


	•	Strings in switch

switch(name) {
    case "admin": ...
}


	•	Numeric literals with underscores

int million = 1_000_000;



⸻

✅ Java 8 (2014) – Functional Revolution
	•	Lambda Expressions

(a, b) -> a + b


	•	Streams API

list.stream().filter(x -> x > 10).collect(Collectors.toList());


	•	Functional Interfaces
	•	Default & Static methods in interfaces
	•	New Date/Time API

LocalDate now = LocalDate.now();



⸻

✅ Java 9 (2017)
	•	JPMS – Java Platform Module System
	•	jshell REPL
	•	Private methods in interfaces
	•	Stream improvements

stream.takeWhile(x -> x < 10);



⸻

✅ Java 10 (2018)
	•	Local variable type inference with var

var name = "Java";



⸻

✅ Java 11 (2018) – LTS Version
	•	New String methods

" Java ".strip();
"line1\nline2".lines();


	•	HTTP Client API
	•	Launch single-file programs

java HelloWorld.java



⸻

✅ Java 12–14 (2019–2020)
	•	Switch Expressions (final in Java 14)

String result = switch(day) {
    case MONDAY -> "Start";
    case FRIDAY -> "End";
    default -> "Mid";
};


	•	Text Blocks (final in Java 15)

String json = """
    {
      "name": "John"
    }
    """;



⸻

✅ Java 15–17 (2020–2021)
	•	Sealed Classes

public sealed class Shape permits Circle, Square {}


	•	Pattern Matching for instanceof

if (obj instanceof String s) {
    System.out.println(s.length());
}


	•	Java 17 is an LTS release

⸻

✅ Java 18–20 (2022–2023)
	•	Simple Web Server (Java 18)
	•	Record Patterns & Pattern Matching for switch (Preview)

⸻

✅ Java 21 (2023) – LTS with Big Features
	•	Record Patterns

record Point(int x, int y) {}
if (obj instanceof Point(int x, int y)) {
    ...
}


	•	Pattern Matching for switch (finalized)
	•	Sequenced Collections

SequencedSet<String> set = ...


	•	Virtual Threads (Preview)

Thread.startVirtualThread(() -> {
    System.out.println("Running in a virtual thread");
});


	•	String Templates (Preview)

String name = "John";
String msg = STR."Hello \{name}!";



⸻

📋 Summary Table

Version	Key Features
Java 7	Try-with-resources, Diamond, String in switch
Java 8	Lambdas, Streams, Date/Time API
Java 9	Modules, jshell
Java 10	var keyword
Java 11	HTTP Client, new String methods
Java 14	Switch expressions
Java 15	Text blocks
Java 17	Sealed classes, pattern matching (instanceof)
Java 21	Virtual threads, Record patterns, String templates


⸻

Let me know if you’d like this in .md file or with collapsible sections for documentation!
