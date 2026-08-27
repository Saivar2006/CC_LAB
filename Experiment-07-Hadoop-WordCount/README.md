# Ex.No: 07-Hadoop-WordCount

# Install Hadoop Single Node Cluster and Run WordCount

## AIM

To find the procedure to set up the one node Hadoop cluster.

## ALGORITHM

1. Install Java as the main prerequisite for Hadoop.
2. Install the SSH server.
3. Generate the SSH key.
4. Add the public key to authorized_keys so that `ssh localhost` can work without a password.
5. Create the Hadoop group and user.
6. Copy `hadoop-2.7.0.tar.gz` to the home directory.
7. Extract Hadoop into `/usr/local/lib/`.
8. Change ownership of the Hadoop installation.
9. Create HDFS NameNode and DataNode directories.
10. Check the Java installation path.
11. Add JAVA_HOME and Hadoop environment variables to `.bashrc`.
12. Reload the environment using `source ~/.bashrc`.
13. Set JAVA_HOME in `hadoop-env.sh`.
14. Configure `core-site.xml`.
15. Configure `yarn-site.xml`.
16. Create `mapred-site.xml` from the template and configure it for YARN.
17. Configure `hdfs-site.xml` with replication and NameNode/DataNode directories.
18. Update `/etc/profile` with JAVA_HOME and PATH.
19. Format the NameNode using `hdfs namenode -format`.
20. Start HDFS using `start-dfs.sh`.
21. Start YARN using `start-yarn.sh`.
22. Verify NameNode, DataNode, SecondaryNameNode, ResourceManager and NodeManager using `jps`.
23. Open the NameNode web interface at `http://localhost:50070`.
24. Create HDFS input directories.
25. Compile the WordCount Java source and create the JAR.
26. Run the WordCount MapReduce job.
27. Display the output using Hadoop FS.

## PROGRAM / CODE

```text
import java.io.IOException;
import java.util.StringTokenizer;
import org.apache.hadoop.conf.Configuration;
import org.apache.hadoop.fs.Path;
import org.apache.hadoop.io.IntWritable;
import org.apache.hadoop.io.Text;
import org.apache.hadoop.mapreduce.Job;
import org.apache.hadoop.mapreduce.Mapper;
import org.apache.hadoop.mapreduce.Reducer;
import org.apache.hadoop.mapreduce.lib.input.FileInputFormat;
import org.apache.hadoop.mapreduce.lib.output.FileOutputFormat;

public class WordCount {
    public static class TokenizerMapper
        extends Mapper<Object, Text, Text, IntWritable> {

        private final static IntWritable one = new IntWritable(1);
        private Text word = new Text();

        public void map(Object key, Text value, Context context)
            throws IOException, InterruptedException {
            StringTokenizer itr = new StringTokenizer(value.toString());
            while (itr.hasMoreTokens()) {
                word.set(itr.nextToken());
                context.write(word, one);
            }
        }
    }

    public static class IntSumReducer
        extends Reducer<Text, IntWritable, Text, IntWritable> {

        private IntWritable result = new IntWritable();

        public void reduce(Text key, Iterable<IntWritable> values,
                            Context context)
            throws IOException, InterruptedException {
            int sum = 0;
            for (IntWritable val : values)
                sum += val.get();

            result.set(sum);
            context.write(key, result);
        }
    }

    public static void main(String[] args) throws Exception {
        Configuration conf = new Configuration();
        Job job = Job.getInstance(conf, "word count");

        job.setJarByClass(WordCount.class);
        job.setMapperClass(TokenizerMapper.class);
        job.setCombinerClass(IntSumReducer.class);
        job.setReducerClass(IntSumReducer.class);

        job.setOutputKeyClass(Text.class);
        job.setOutputValueClass(IntWritable.class);

        FileInputFormat.addInputPath(job, new Path(args[0]));
        FileOutputFormat.setOutputPath(job, new Path(args[1]));

        System.exit(job.waitForCompletion(true) ? 0 : 1);
    }
}
```

## SAMPLE INPUT

```text
Input text containing the words:
Bye
Goodbye
Hadoop Hadoop
Hello Hello
World World
```

## SAMPLE OUTPUT

```text
Bye 1
Goodbye 1
Hadoop 2
Hello 2
World 2
```

## RESULT

Thus the one node Hadoop cluster is installed and word count program to demonstrate the Map and Reduce task is done successfully.

---

### Files

- `README.md` – Complete experiment record
- `screenshots/` – Place your actual lab screenshots here

> **Note:** The content is organized from the supplied Cloud Computing Lab Manual. Where the manual gives a procedure rather than an algorithm or source program, that original procedure is preserved instead of inventing unrelated content.
