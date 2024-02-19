# Ant를 사용한 셸 스크립트 생성 예제

이 예제는 Ant를 사용하여 Linux용 셸 스크립트를 생성하는 과정을 보여줍니다.

## 1. `build.xml`

```xml
<project name="MyProject" basedir="." default="create-linux-sh">

    <!-- Define properties -->
    <property name="script.name" value="my_script.sh"/>
    <property name="output.dir" value="C:/test"/>

    <target name="create-linux-sh">
        <!-- Create the Linux shell script -->
        <echo file="${output.dir}/${script.name}">
            <![CDATA[
#!/bin/bash
# Your script content here
echo "Hello, Linux!"
            ]]>
        </echo>
        <echo message="Linux shell script created at ${output.dir}/${script.name}"/>
    </target>

</project>
```

## 2. 코드에 대한 설명

# <project>
- **name**: 프로젝트의 이름을 지정합니다.
- **basedir**: 기본 디렉토리를 설정합니다.
- **default**: 기본 타겟을 지정합니다.

# <property>

- **script.name**: 생성할 스크립트 파일의 이름입니다. 여기서는 my_script.sh입니다.
- **output.dir**: 생성된 스크립트 파일을 저장할 디렉토리의 경로입니다.

# <target>

- **create-linux-sh**: 이 타겟은 Linux 쉘 스크립트를 생성하는 작업을 정의합니다.
- **echo**: output.dir 경로에 script.name 이름으로 새 스크립트 파일을 생성합니다.
- **CDATA**: 스크립트 내용을 삽입합니다. 이는 특수 문자를 이스케이프하지 않고 포함할 수 있도록 합니다.
- **echo**: 스크립트가 성공적으로 생성되었음을 알리는 메시지를 출력합니다.

## 3. 실행 결과
![image](https://github.com/auspicious0/AntBuildEx02_SH/assets/108572025/0814454a-b837-4e34-866b-03fab793448b)

