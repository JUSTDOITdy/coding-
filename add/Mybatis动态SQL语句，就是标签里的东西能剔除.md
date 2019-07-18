# Mybatis动态SQL语句，就是<>标签里的东西能剔除

##### 1.if，if判断的意思，判断test=“”语句，没有值就把<if></if>里的东西删除，是在where 后面用 ，当有多个条件，一般需要和where一起

`select * from user where username=#{username} and sex=#{sex}`

select * from user where

<if test="username != null">

​	username = #{username}

</if>

	<if test="username != null">
  	    and sex=#{sex}
</if>

####  2.where，where能剔除条件里的and、or，其实是个trim的变体

  select * from user
    <where>
        <if test="username != null">
           username=#{username}
        </if>
         

​    <if test="username != null">
​       and sex=#{sex}
​    </if>
</where> 

