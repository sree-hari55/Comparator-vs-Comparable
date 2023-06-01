# Comparator-vs-Comparable


# Comparable :
1) Comparable provides a single sorting sequence. In other words, we can sort the collection on the basis of a single element such as id, name, and price.
2) Comparable affects the original class (the actual class is modified)
3) Comparable provides compareTo() method to sort elements.
4) Comparable is present on java.lang package.
5) We can sort the list elements of Comparable type by Collections.sort(List) method

# Comparator :

1) The Comparator provides multiple sorting sequences. In other words, we can sort the collection on the basis of multiple elements such as id, name,` price, etc.
2) Comparator provides compare() method to sort elements.
3) A Comparator is present in java.util package.
4) We can sort the list elements of Comparator type by Collections.sort(List, Comparator) method.


# Comparable example code 

public class Student implements Comparable<Student>{

    private int id;
    private String name;

    public Student(int id, String name) {
        this.id = id;
        this.name = name;
    }

    public int getId() {
        return id;
    }

    public void setId(int id) {
        this.id = id;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    @Override
    public boolean equals(Object obj){
        if (this == obj) {
            return true;
        }
        if (obj == null || getClass() != obj.getClass()) {
            return false;
        }
        Student student = (Student) obj;
        return id == student.id && Objects.equals(name, student.name);
    }


    @Override
    public int compareTo(Student student) {
        if (id == student.id){
            return 0;
        }else if (id > student.id){
            return  1;
        }else{
            return -1;
        }
    }
}

public class ComparableExample {

	public static void main(String[] args) {
		Student student=new Student(103,"okay");
		Student student1=new Student(101,"okay2");
		Student student2=new Student(102,"okay3");

		List<Student> l=new ArrayList<>();
		l.add(student);
		l.add(student1);
		l.add(student2);
		System.out.println(l);
	
		Collections.sort(l);
		
		System.out.println(l);

	}

}  
  
#Comparator example code 
 
  public class IdComparator implements Comparator<Student> {
    @Override
    public int compare(Student student1, Student student2) {
        if (student1.getId() ==  student2.getId()){
            return 0;
        }else if (student1.getId() > student2.getId()){
            return 1;
        } else {
            return -1;
        }
    }
}
  
public class NameComparator implements Comparator<Student> {
    @Override
    public int compare(Student student1, Student student2) {
        return student1.getName().compareTo(student2.getName());
    }
}
  
public class ComparableExample {

	public static void main(String[] args) {
		Student student=new Student(103,"okay");
		Student student1=new Student(101,"okay2");
		Student student2=new Student(102,"okay3");

		List<Student> l=new ArrayList<>();
		l.add(student);
		l.add(student1);
		l.add(student2);
		System.out.println(l);
	
		Collections.sort(studentList, new NameComparator());
or
Collections.sort(studentList, new IdComparator());
		
		System.out.println(l);

	}

}   
