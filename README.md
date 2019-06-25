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
     * @JMS\Serializer\Annotation\SerializedName("id")
     * @JMS\Serializer\Annotation\Groups({"all"})
     * @JMS\Serializer\Annotation\VirtualProperty
    */
    public function getRestId()
    {
        return $this->getId();
    }
    
    /**
     * @JMS\Serializer\Annotation\SerializedName("label")
     * @JMS\Serializer\Annotation\Groups({"myGroup"})
     * @JMS\Serializer\Annotation\VirtualProperty
    */
    public function getRestLabel()
    {
        return $this->getLabel();
    }

    /**
     * @JMS\Serializer\Annotation\SerializedName("is_active")
     * @JMS\Serializer\Annotation\Groups({"myGroup", "anotherGroup"})
     * @JMS\Serializer\Annotation\VirtualProperty
    */
    public function getRestIsActive()
    {
        return $this->getIsActive();
    }

    ...
}
