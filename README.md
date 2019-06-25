This a propel behavior to auto-generate methods of FOSRestBundle.
Installation

composer require deblan/fos-rest-behavior
How to

<table name="foo">
    <column name="id" type="INTEGER" primaryKey="true" autoIncrement="true" required="true" />
    <column name="label" type="VARCHAR" size="256"/>
    <column name="is_active" type="BOOLEAN" size="1"/>

    <behavior name="Deblan\Propel\Behavior\FOSRestBehavior">
        <parameter name="id" value="all"/>
        <parameter name="label" value="myGroup"/>
        <parameter name="is_active" value="myGroup, anotherGroup"/>
    </behavior>
</table>

After the model generation, the abstract class Foo will be updated with new annotations and methods:

/**
 * [...]
 *
 * @JMS\Serializer\Annotation\ExclusionPolicy("all")
 */
abstract class Foo implements ActiveRecordInterface
{
    ...

    /**
     * @JMS\Serializer\Annotation\SerializedName("id")<a href="https://www.imdb.com/list/ls044443166/">Watch Child's Play Online</a><br>
     * @JMS\Serializer\Annotation\Groups({"all"})
     * @JMS\Serializer\Annotation\VirtualProperty
    */
    public function getRestId()
    {
        return $this->getId();<a href="https://www.imdb.com/list/ls044443161/">Watch Toy Story 4 Online</a><br>
    }
    <a href="https://www.imdb.com/list/ls044443168/">Watch Child's Play Online</a><br>






<a href="https://www.imdb.com/list/ls044443130/">Watch Rocketman Online</a><br>
<a href="https://www.imdb.com/list/ls044443112/">Watch Avengers: Endgame Online</a><br>
<a href="https://www.imdb.com/list/ls044443114/">Watch John Wick: Chapter 3 - Parabellum Online</a><br>

    /**
     * @JMS\Serializer\Annotation\SerializedName("label")
     * @JMS\Serializer\Annotation\Groups({"myGroup"})<a href="https://www.imdb.com/list/ls044443136/">Watch Shaft Online</a><br>
     * @JMS\Serializer\Annotation\VirtualProperty
    */
    public function getRestLabel()<a href="https://www.imdb.com/list/ls044443139/">Watch Toy Story 4 Online</a><br>
    {
        return $this->getLabel();
    }

    /**
     * @JMS\Serializer\Annotation\SerializedName("is_active")
     * @JMS\Serializer\Annotation\Groups({"myGroup", "anotherGroup"})<a href="https://www.imdb.com/list/ls044443132/">Watch Men in Black International Online</a><br>
     * @JMS\Serializer\Annotation\VirtualProperty<a href="https://www.imdb.com/list/ls044443131/">Watch The Secret Life of Pets 2 Online</a><br>
    */
    public function getRestIsActive()
    {
        return $this->getIsActive();
    }

    ...
}
