Redis Basic
Overview
This project provides an introduction to Redis, a powerful in-memory key-value data store. It covers basic Redis operations such as string manipulation, list operations, hash operations, set operations, and more, implemented using Python.

Project Structure
exercise.py: The main Python file where the Redis operations and a custom Redis-like class are implemented.
tests/: Directory containing test cases for the implemented Redis operations.
Prerequisites
Python 3.x installed on your machine.
Redis server running locally or accessible remotely.
Installation
Clone the repository:

bash
Copy code
git clone https://github.com/yourusername/redis-basic.git
cd redis-basic
Install dependencies:
There are no external dependencies for this project, as it uses core Python libraries. However, to interact with an actual Redis server, you may want to install redis-py:

bash
Copy code
pip install redis
Run Redis server:
Ensure that a Redis server is running locally. You can start one using Docker:

bash
Copy code
docker run --name redis-basic -p 6379:6379 -d redis
Basic Redis Operations
String Operations
SET key value: Set the value of a key.
GET key: Get the value of a key.
DEL key: Delete a key.
INCR key: Increment the integer value of a key by one.
DECR key: Decrement the integer value of a key by one.
List Operations
LPUSH key value: Prepend one or more values to a list.
RPUSH key value: Append one or more values to the end of a list.
LPOP key: Remove and return the first element of the list.
RPOP key: Remove and return the last element of the list.
LRANGE key start stop: Get a range of elements from a list.
Hash Operations
HSET key field value: Set the value of a field in a hash.
HGET key field: Get the value of a field in a hash.
HDEL key field: Delete a field from a hash.
HGETALL key: Get all fields and values in a hash.
Set Operations
SADD key member: Add a member to a set.
SREM key member: Remove a member from a set.
SMEMBERS key: Get all the members in a set.
Sorted Set Operations
ZADD key score member: Add a member to a sorted set with a given score.
ZRANGE key start stop: Get a range of members in a sorted set, by index.
ZREM key member: Remove a member from a sorted set.
Expire and TTL Operations
EXPIRE key seconds: Set a timeout on a key.
TTL key: Get the remaining time to live of a key.
Usage
You can use the provided RedisLike class to simulate Redis operations locally without connecting to a real Redis server. Here's an example of how to use it:

python
Copy code
from exercise import RedisLike

# Initialize the RedisLike object
redis = RedisLike()

# String operations
redis.SET("mykey", "value")
print(redis.GET("mykey"))  # Output: value

# List operations
redis.LPUSH("mylist", "first")
redis.RPUSH("mylist", "last")
print(redis.LRANGE("mylist", 0, -1))  # Output: ['first', 'last']

# Hash operations
redis.HSET("myhash", "field1", "value1")
print(redis.HGETALL("myhash"))  # Output: {'field1': 'value1'}
Testing
To run the tests for the implemented Redis operations:

bash
Copy code
python -m unittest discover tests/
Contributing
Contributions are welcome! Please feel free to submit a pull request or open an issue for any bug reports or feature requests.
