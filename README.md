# 13.9-programming-assignment
import java.util.Objects;

public class Circle extends GeometricObject implements Comparable<Circle> {

    private double radius;

    public Circle() {
    }

    public Circle(double radius) {
        this.radius = radius;
    }

    public double getRadius() {
        return radius;
    }

    public void setRadius(double radius) {
        this.radius = radius;
    }

    @Override
    public double getArea() {
        return Math.PI * radius * radius;
    }

    @Override
    public double getPerimeter() {
        return 2 * Math.PI * radius;
    }

    @Override
    public boolean equals(Object obj) {
        if (obj == this) {
            return true;
        }
        if (obj instanceof Circle) {
            Circle other = (Circle) obj;
            return radius == other.radius;
        }
        return false;
    }

    @Override
    public int hashCode() {
        return Objects.hash(radius);
    }

    @Override
    public int compareTo(Circle other) {
        return Double.compare(radius, other.radius);
    }
}
