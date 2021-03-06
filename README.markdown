scalatest-junit4runner is a [JUnit4 Runner](http://www.junit.org/) for [ScalaTest](http://www.artima.com/scalatest/)

It lets you run ScalaTests from both Maven and your JUnit4 enabled IDE by annotating your tests as shown in the example below

1. Install
----------------

    git clone git://github.com/notnoop/scalatest-junit4runner.git
    cd scalatest-junit4runner
    mvn clean install


2. Add as a dependency
---------------------------

    <dependency>
      <groupId>com.jteigen.scalatest</groupId>
      <artifactId>junit4runner</artifactId>
      <version>1.0-SNAPSHOT</version>
      <scope>test</scope>
    </dependency>

3. Use
----------------------

    import com.jteigen.scalatest.JUnit4Runner
    import org.junit.runner.RunWith
    import org.scalatest.matchers.ShouldMatchers
    import org.scalatest.Spec

    @RunWith(classOf[JUnit4Runner])
    class SimpleTest extends Spec with ShouldMatchers {
      describe("Demo"){
        it("should run"){
          1 + 1 should be (2)
        }

        ignore("should ignore"){
          1 + 1 should be (3) // doesn't fail as the test is ignored
        }

        it("should crash and burn!"){
          1 + 1 should be (3)
        }
      }
    }
