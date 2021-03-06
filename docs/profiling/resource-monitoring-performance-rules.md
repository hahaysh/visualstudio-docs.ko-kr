---
title: 리소스 모니터링 성능 규칙 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: f0f77faf-0a05-4718-a2c5-47934be40868
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 433a89ae2a7cf8c9e20ec3711dcebe1514ae021b
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="resource-monitoring-performance-rules"></a>리소스 모니터링 성능 규칙
리소스 모니터링 범주의 성능 메시지는 응용 프로그램의 성능에 대한 추가 데이터를 제공합니다. 이 데이터를 사용하여 성능 문제를 분석할 수 있습니다. 이러한 규칙은 정보를 제공하며 모든 프로파일링 실행에 대해 보고됩니다.  
  
|||  
|-|-|  
|[DA0501: 프로파일링되고 있는 프로세스의 평균 CPU 사용입니다.](../profiling/da0501-average-cpu-consumption-by-the-process-being-profiled.md)|이 메시지는 응용 프로그램에서 명령을 실행할 때 프로세서가 사용 중이었던 시간의 백분율을 보고합니다. 보고된 값은 프로파일링되는 프로세스가 활성 상태였던 모든 측정 간격에 대한 평균입니다.|  
|[DA0502: 프로파일링되고 있는 프로세스의 최대 CPU 사용입니다.](../profiling/da0502-maximum-cpu-consumption-by-the-process-being-profiled.md)|이 메시지는 응용 프로그램에서 명령을 실행할 때 프로세서가 사용 중이었던 시간의 최대 백분율을 보고합니다. 보고된 값은 프로파일링되는 프로세스가 활성 상태였던 모든 측정 간격 중에 보고된 최대값입니다.|  
|[DA0503: 프로파일링되고 있는 프로세스의 평균 작업 집합(바이트 단위)입니다.](../profiling/da0503-average-working-set-in-bytes-for-the-process-being-profiled.md)|이 메시지는 프로파일링이 활성 상태였을 때 프로세스에서 사용 중이었던 실제 메모리의 평균 크기(바이트)를 보고합니다. 이 실제 메모리의 측정값은 작업 집합이라고 합니다.|  
|[DA0504: 프로파일링되고 있는 프로세스의 최대 작업 집합(바이트 단위)입니다.](../profiling/da0504-maximum-working-set-in-bytes-for-the-process-being-profiled.md)|이 메시지는 프로파일링이 활성 상태였을 때 프로세스에서 사용 중이었던 실제 메모리의 최대 크기(바이트)를 보고합니다.|  
|[DA0505: 프로파일링되고 있는 프로세스에 할당된 평균 전용 바이트입니다.](../profiling/da0505-average-private-bytes-allocated-for-the-process-being-profiled.md)|이 메시지는 프로파일링이 활성 상태였을 때 프로세스가 할당한 가상 메모리의 평균 크기(바이트)를 보고합니다. 이 가상 메모리의 측정값은 *전용 바이트*라고 합니다. 전용 바이트는 프로세스 내에서 실행되는 스레드만 액세스할 수 있는, 프로세스에 의해 할당된 가상 메모리 위치를 나타냅니다.|  
|[DA0506: 프로파일링되고 있는 프로세스에 할당된 최대 전용 바이트입니다.](../profiling/da0506-maximum-private-bytes-allocated-for-the-process-being-profiled.md)|이 메시지는 프로파일링이 활성 상태였을 때 프로세스가 할당한 가상 메모리의 최대 크기(전용 바이트)를 보고합니다.|