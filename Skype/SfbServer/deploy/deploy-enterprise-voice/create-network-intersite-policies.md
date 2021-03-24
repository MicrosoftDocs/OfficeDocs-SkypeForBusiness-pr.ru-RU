---
title: Создание сетевых межсетных политик в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b0714aae-55dc-4587-b718-34a03f596b22
description: Создайте сетевые политики межсайтов, которые используются Корпоративная голосовая связь управления приемом вызовов в Skype для бизнеса Server.
ms.openlocfilehash: 7c0ca45c691ab1ef70d3660c3d49a08c40bdd40d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093087"
---
# <a name="create-network-intersite-policies-in-skype-for-business-server"></a>Создание сетевых межсетных политик в Skype для бизнеса Server
 
Создайте сетевые политики межсайтов, которые используются Корпоративная голосовая связь управления приемом вызовов в Skype для бизнеса Server. 
  
Политика межсайтовой сети определяет ограничения пропускной способности между сайтами, у которых между ними есть прямые связи WAN.
  
> [!IMPORTANT]
> Политика межсайтов сети  необходима только в том случае, если между двумя сетевыми сайтами существует прямая перекрестная связь.
  
В примере топологии Северной Америки существует прямая связь между сайтами Reno и Albuquerque. Для этих двух сайтов требуется политика межсайтов, которая применяет соответствующий профиль политики пропускной способности. В следующем примере применяется 20Mb_Link профиль.
  
### <a name="to-create-a-network-inter-site-policy"></a>Создание сетевой политики межсайтов

1. Запустите оболочку управления Skype для бизнес-серверов: нажмите кнопку Начните, щелкните Все **программы,** щелкните Skype для бизнеса **2015,** а затем нажмите **кнопку Skype для управления бизнес-серверами.**
    
2. Запустите New-CsNetworkInterSitePolicy, чтобы создать сетевые политики межсайтов и применить соответствующий профиль политики пропускной способности для двух сайтов с прямым перекрестным соединением. Например, выполните команду:
    
   ```powershell
   New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link
   ```

3. Повторите шаг 2 по мере необходимости для создания сетевых политик межсайтов для всех пар сетевых сайтов, которые имеют прямую перекрестную связь.
    
## <a name="see-also"></a>См. также

[New-CsNetworkInterSitePolicy](/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps)
  
[Get-CsNetworkInterSitePolicy](/powershell/module/skype/get-csnetworkintersitepolicy?view=skype-ps)
  
[Set-CsNetworkInterSitePolicy](/powershell/module/skype/set-csnetworkintersitepolicy?view=skype-ps)
  
[Remove-CsNetworkInterSitePolicy](/powershell/module/skype/remove-csnetworkintersitepolicy?view=skype-ps)