title: LogicalRDD

# LogicalRDD -- Logical Scan Over RDD

`LogicalRDD` is a link:spark-sql-LogicalPlan-LeafNode.adoc[leaf logical operator] with <<newInstance, MultiInstanceRelation>> support for a logical representation of a scan over <<rdd, RDD of internal binary rows>>.

`LogicalRDD` is <<creating-instance, created>> when:

* `Dataset` is requested to <<spark-sql-Dataset-untyped-transformations.adoc#checkpoint, checkpoint>>

* `SparkSession` is requested to link:SparkSession.md#internalCreateDataFrame[create a DataFrame from an RDD of internal binary rows]

!!! note
    `LogicalRDD` is resolved to [RDDScanExec](../physical-operators/RDDScanExec.md) when [BasicOperators](../execution-planning-strategies/BasicOperators.md#LogicalRDD) execution planning strategy is executed.

=== [[newInstance]] `newInstance` Method

[source, scala]
----
newInstance(): LogicalRDD.this.type
----

NOTE: `newInstance` is part of link:spark-sql-MultiInstanceRelation.adoc#newInstance[MultiInstanceRelation Contract] to...FIXME.

`newInstance`...FIXME

=== [[computeStats]] Computing Statistics -- `computeStats` Method

[source, scala]
----
computeStats(): Statistics
----

NOTE: `computeStats` is part of link:spark-sql-LogicalPlan-LeafNode.adoc#computeStats[LeafNode Contract] to compute statistics for link:spark-sql-cost-based-optimization.adoc[cost-based optimizer].

`computeStats`...FIXME

=== [[creating-instance]] Creating LogicalRDD Instance

`LogicalRDD` takes the following when created:

* [[output]] Output schema link:spark-sql-Expression-Attribute.adoc[attributes]
* [[rdd]] `RDD` of link:spark-sql-InternalRow.adoc[internal binary rows]
* [[outputPartitioning]] link:spark-sql-SparkPlan-Partitioning.adoc[Partitioning]
* [[outputOrdering]] Output ordering (`SortOrder`)
* [[isStreaming]] `isStreaming` flag
* [[session]] link:SparkSession.md[SparkSession]