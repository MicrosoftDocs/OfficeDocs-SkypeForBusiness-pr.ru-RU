---
title: Развертывание функций высокой доступности и аварийного восстановления
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 21007bad-62ce-4553-98e0-02aaa1345781
description: Skype для бизнеса Server обеспечивает высокую доступность с объединением серверов, восстановлением аварийности с сопряжением пула и несколькими режимами высокой доступности back End Server, включая группы доступности AlwaysOn, зеркальное зеркальное отражение баз данных и кластеризация SQL сбой.
ms.openlocfilehash: df77652840c127e011042172f618eba37d916f85
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2022
ms.locfileid: "62394327"
---
# <a name="deploy-high-availability-and-disaster-recovery"></a>Развертывание функций высокой доступности и аварийного восстановления
 
Skype для бизнеса Server обеспечивает высокую доступность с объединением серверов, восстановлением аварийности с сопряжением пула и несколькими режимами высокой доступности back End Server, включая группы доступности AlwaysOn, зеркальное зеркальное отражение баз данных и кластеризация SQL сбой. 
  
Высокая доступность означает обеспечение доступности Skype для бизнеса Server, даже если один или несколько серверов будут недоступны. Аварийное восстановление означает сохранение служб в случае стихийного или вызванного человеком стихийного бедствия и сохранение как можно больше данных до катастрофы.
  
В этом разделе рассказывается о развертывании этих функций, а также рассказывается о том, какие действия можно предпринять для высокой доступности и аварийного восстановления для некоторых других ролей сервера.

> [!NOTE]
> SQL зеркальное отражение доступно в Skype для бизнеса Server 2015 г., но больше не поддерживается Skype для бизнеса Server 2019 г. В 2019 г. предпочтительны группы доступности AlwaysOn, экземпляры кластера неудачной передачи alwaysOn и SQL Skype для бизнеса Server кластеризация неудачи.
  
## <a name="related-sections"></a>Связанные разделы

[Планирование высокой доступности и аварийного восстановления в Skype для бизнеса Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
  
## <a name="see-also"></a>См. также

[Развертывание группы доступности AlwaysOn на сервере back end в Skype для бизнеса Server](alwayson-availability-group.md)

[Развертывание парных пулов переднего конца для аварийного восстановления в Skype для бизнеса Server](front-end-pools-for-disaster-recovery.md)
  
[Развертывание SQL для высокой доступности back End Server в Skype для бизнеса Server 2015 г.](sql-mirroring-for-high-availability.md)
  
