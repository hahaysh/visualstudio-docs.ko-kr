---
title: 코드 분석을 위한 예제 c + + 프로젝트
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: sample
helpviewer_keywords:
- demo sample [Visual Studio ALM]
- code analysis, samples
ms.assetid: 09e1b9f7-5916-4ed6-a001-5c2d7e710682
author: mikeblome
ms.author: mblome
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: aafbaaf682852adaea8f20a1373ea1ae4b025fad
ms.sourcegitcommit: fe5a72bc4c291500f0bf4d6e0778107eb8c905f5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="sample-c-project-for-code-analysis"></a>코드 분석을 위한 예제 c + + 프로젝트

이 다음 절차에 대 한 예제를 만드는 방법을 보여 줍니다. [연습: 분석 C/c + + 코드 오류에 대 한](../code-quality/walkthrough-analyzing-c-cpp-code-for-defects.md)합니다. 절차 만들기:

- Visual Studio 솔루션 이름이 CppDemo입니다.

- 정적 라이브러리 프로젝트 이름이 CodeDefects입니다.

- 정적 라이브러리 프로젝트 이름이 주석입니다.

절차는 헤더에 대 한도 코드를 제공 하 고 *.cpp* 정적 라이브러리에 대 한 파일입니다.

## <a name="create-the-cppdemo-solution-and-the-codedefects-project"></a>CppDemo 솔루션과 CodeDefects 프로젝트 만들기

1. 클릭는 **파일** 메뉴에서 **새로**, 클릭 하 고 **새 프로젝트**합니다.

2. 에 **프로젝트 형식** 목록 트리, Visual c + + VS의 기본 언어가 없는 경우 확장 **다른 언어**합니다.

3. 확장 **Visual c + +**, 클릭 하 고 **일반**합니다.

4. **템플릿**, 클릭 **빈 프로젝트**합니다.

5. 에 **이름** 텍스트 상자에서 **CodeDefects**합니다.

6. 선택 된 **솔루션용 디렉터리 만들기** 확인란 합니다.

7. 에 **솔루션 이름** 텍스트 상자에서 **CppDemo**합니다.

## <a name="configure-the-codedefects-project-as-a-static-library"></a>정적 라이브러리 CodeDefects 프로젝트를 구성 하는 중

1. 솔루션 탐색기에서 마우스 오른쪽 단추로 클릭 **CodeDefects** 클릭 하 고 **속성**합니다.

2. 확장 **구성 속성** 클릭 하 고 **일반**합니다.

3. 에 **일반** 목록에서 열에서 옆에 텍스트를 선택 **대상 확장명**, 한 다음 입력 **.lib**합니다.

4. **프로젝트 기본값**, 해당 열 옆에 클릭 **구성 유형**, 클릭 하 고 **정적 라이브러리 (.lib)** 합니다.

## <a name="add-the-header-and-source-file-to-the-codedefects-project"></a>CodeDefects 프로젝트는 헤더 및 원본 파일을 추가

1. 솔루션 탐색기에서 확장 **CodeDefects**를 마우스 오른쪽 단추로 클릭 **헤더 파일**, 클릭 **추가**, 클릭 하 고 **새 항목**합니다.

2. 에 **새 항목 추가** 대화 상자를 클릭 **코드**, 클릭 하 고 **헤더 파일 (.h)** 합니다.

3. 에 **이름** 상자에 입력 합니다 **Bug.h** 클릭 하 고 **추가**합니다.

4. 다음 코드를 복사 하 고에 붙여 넣은 *Bug.h* Visual Studio 편집기에서 파일입니다.

    ```cpp
    #include <windows.h>

    //
    //These 3 functions are consumed by the sample
    //  but are not defined. This project cannot be linked!
    //

    bool CheckDomain( LPCSTR );
    HRESULT ReadUserAccount();

    //
    //These constants define the common sizes of the
    //  user account information throughout the program
    //

    const int USER_ACCOUNT_LEN = 256;
    const int ACCOUNT_DOMAIN_LEN = 128;
    ```

5. 솔루션 탐색기에서 마우스 오른쪽 단추로 클릭 **소스 파일**, 가리킨 **새로**, 클릭 하 고 **새 항목**합니다.

6. 에 **새 항목 추가** 대화 상자를 클릭 하 여 **c + + 파일 (.cpp)**

7. 에 **이름** 상자에 입력 합니다 **Bug.cpp** 클릭 하 고 **추가**합니다.

8. 다음 코드를 복사 하 고에 붙여 넣은 *Bug.cpp* Visual Studio 편집기에서 파일입니다.

    ```cpp
    #include <stdlib.h>
    #include "Bug.h"

    // the user account
    TCHAR g_userAccount[USER_ACCOUNT_LEN] = "";
    int len = 0;

    bool ProcessDomain()
    {
        TCHAR* domain = new TCHAR[ACCOUNT_DOMAIN_LEN];
        // ReadUserAccount gets a 'domain\user' input from
        //the user into the global 'g_userAccount'
        if (ReadUserAccount() )
        {

            // Copies part of the string prior to the '\'
            // character onto the 'domain' buffer
            for( len = 0 ; (len < ACCOUNT_DOMAIN_LEN) && (g_userAccount[len] != '\0') ; len++  )
            {
                if ( g_userAccount[len] == '\\' )
                {
                    // Stops copying on the domain and user separator ('\')
                    break;
                }
                domain[len] = g_userAccount[len];
            }
            if((len= ACCOUNT_DOMAIN_LEN) || (g_userAccount[len] != '\\'))
            {
                // '\' was not found. Invalid domain\user string.
                delete [] domain;
                return false;
            }
            else
            {
                domain[len]='\0';
            }
            // Process domain string
            bool result = CheckDomain( domain );

            delete[] domain;
            return result;
        }
        return false;
    }

    int path_dependent(int n)
    {
        int i;
        int j;
        if (n == 0)
            i = 1;
        else
            j = 1;
        return i+j;
    }
    ```

9. 클릭는 **파일** 메뉴를 차례로 클릭 **모두 저장**합니다.

## <a name="add-the-annotations-project-and-configure-it-as-a-static-library"></a>주석 프로젝트를 추가 하 고 정적 라이브러리로 구성

1. 솔루션 탐색기에서 클릭 **CppDemo**, 가리킨 **추가**, 클릭 하 고 **새 프로젝트**합니다.

2. 에 **새 프로젝트 추가** 대화 상자, Visual c + +, 클릭 **일반**, 클릭 하 고 **빈 프로젝트**합니다.

3. 에 **이름** 텍스트 상자에서 **주석**, 클릭 하 고 **추가**합니다.

4. 솔루션 탐색기에서 마우스 오른쪽 단추로 클릭 **주석** 클릭 하 고 **속성**합니다.

5. 확장 **구성 속성** 클릭 하 고 **일반**합니다.

6. 에 **일반** 목록에서 열에서 옆에 텍스트를 선택 **대상 확장명**, 한 다음 입력 **.lib**합니다.

7. **프로젝트 기본값**, 해당 열 옆에 클릭 **구성 유형**, 클릭 하 고 **정적 라이브러리 (.lib)** 합니다.

## <a name="add-the-header-file-and-source-file-to-the-annotations-project"></a>소스 파일과 헤더 파일 주석 프로젝트에 추가

1. 솔루션 탐색기에서 확장 **주석**를 마우스 오른쪽 단추로 클릭 **헤더 파일**, 클릭 **추가**, 클릭 하 고 **새 항목**합니다.

2. 에 **새 항목 추가** 대화 상자를 클릭 **헤더 파일 (.h)** 합니다.

3. 에 **이름** 상자에 입력 합니다 **annotations.h** 클릭 하 고 **추가**합니다.

4. 다음 코드를 복사 하 고에 붙여 넣은 *annotations.h* Visual Studio 편집기에서 파일입니다.

    ```cpp
    #include <CodeAnalysis/SourceAnnotations.h>

    struct LinkedList
    {
        struct LinkedList* next;
        int data;
    };

    typedef struct LinkedList LinkedList;

    [returnvalue:SA_Post( Null=SA_Maybe )] LinkedList* AllocateNode();

    ```

5. 솔루션 탐색기에서 마우스 오른쪽 단추로 클릭 **소스 파일**, 가리킨 **새로**, 클릭 하 고 **새 항목**합니다.

6. 에 **새 항목 추가** 대화 상자를 클릭 **코드** 클릭 하 고 **c + + 파일 (.cpp)**

7. 에 **이름** 상자에 입력 합니다 **annotations.cpp** 클릭 하 고 **추가**합니다.

8. 다음 코드를 복사 하 고에 붙여 넣은 *annotations.cpp* Visual Studio 편집기에서 파일입니다.

    ```cpp
    #include <CodeAnalysis/SourceAnnotations.h>
    #include <windows.h>
    #include <stdlib.h>
    #include "annotations.h"

    LinkedList* AddTail( LinkedList *node, int value )
    {
        LinkedList *newNode = NULL;

        // finds the last node
        while ( node->next != NULL )
        {
            node = node->next;
        }

        // appends the new node
        newNode = AllocateNode();
        newNode->data = value;
        newNode->next = 0;
        node->next = newNode;

        return newNode;
    }

    ```

9. 클릭는 **파일** 메뉴를 차례로 클릭 **모두 저장**합니다.
