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
