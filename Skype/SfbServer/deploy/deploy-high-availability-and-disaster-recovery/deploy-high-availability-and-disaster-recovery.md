---
title: Развертывание функций высокой доступности и аварийного восстановления
ms.author: heidip
author: microsoftheidi
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 21007bad-62ce-4553-98e0-02aaa1345781
description: Скайп для Business Server предлагает высокой доступности с помощью пула аварийного восстановления с помощью связывания пула и нескольких режимах Тыловой сервер высокой доступности, включая группы обеспечения доступности AlwaysOn, зеркальное отображение базы данных и отказоустойчивый кластер SQL server.
ms.openlocfilehash: c3741527b83634d8a3571daa2623af55806e7f19
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "20993601"
---
# <a name="deploy-high-availability-and-disaster-recovery"></a>Развертывание функций высокой доступности и аварийного восстановления
 
Скайп для Business Server предлагает высокой доступности с помощью пула аварийного восстановления с помощью связывания пула и нескольких режимах Тыловой сервер высокой доступности, включая группы обеспечения доступности AlwaysOn, зеркальное отображение базы данных и отказоустойчивый кластер SQL server. 
  
Высокая доступность относится к проверке того, что Скайп для служб Business Server доступны даже в том случае, если один или несколько серверов, тем ниже. Аварийное восстановление охватывает службы хранения переход в случае аварии природные или отдела, возникающие и сохранения данных из до аварии по мере возможности.
  
В этом разделе рассматривается развертывание этих компонентов, а также процедуры по настройке высокой доступности и аварийного восстановления для остальных ролей сервера.

> [!NOTE]
> Зеркальное отображение SQL доступна в Скайп для Business Server 2015, но в Скайп Business Server 2019 больше не поддерживается. Методы кластеризации отработки отказа группы обеспечения доступности AlwaysOn, экземпляры кластера AlwaysOn отработки отказа (FCI) и SQL, являются предпочтительными с Скайп для Business Server 2019.
  
## <a name="related-sections"></a>Связанные разделы

[Планирование высокой доступности и аварийного восстановления в Скайп Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
  
## <a name="see-also"></a>См. также

[Развертывание группы обеспечения доступности AlwaysOn на сервере заднего плана в Скайп for Business Server](alwayson-availability-group.md)

[Развертывание парных пулов переднего плана для аварийного восстановления в Скайп for Business Server](front-end-pools-for-disaster-recovery.md)
  
[Развертывание зеркального отображения SQL Server для обеспечения высокой доступности внутреннего сервера в Skype для бизнеса Server 2015](sql-mirroring-for-high-availability.md)
  
