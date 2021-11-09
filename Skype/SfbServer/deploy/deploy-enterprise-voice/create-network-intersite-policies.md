---
title: Создание сетевых межсетных политик в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b0714aae-55dc-4587-b718-34a03f596b22
description: Создайте сетевые политики межсайтов, которые используются Корпоративная голосовая связь управления приемом вызовов в Skype для бизнеса Server.
ms.openlocfilehash: 3510a80935bd19fc6ac36904003f744fd7e65cf5
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60841891"
---
# <a name="create-network-intersite-policies-in-skype-for-business-server"></a>Создание сетевых межсетных политик в Skype для бизнеса Server
 
Создайте сетевые политики межсайтов, которые используются Корпоративная голосовая связь управления приемом вызовов в Skype для бизнеса Server. 
  
Политика межсайтовой сети определяет ограничения пропускной способности между сайтами, у которых между ними есть прямые связи WAN.
  
> [!IMPORTANT]
> Политика межсайтов сети  необходима только в том случае, если между двумя сетевыми сайтами существует прямая перекрестная связь.
  
В примере топологии Северной Америки существует прямая связь между сайтами Reno и Albuquerque. Для этих двух сайтов требуется политика межсайтов, которая применяет соответствующий профиль политики пропускной способности. В следующем примере применяется 20Mb_Link профиль.
  
### <a name="to-create-a-network-inter-site-policy"></a>Создание сетевой политики межсайтов

1. Запустите Skype для бизнеса Server: нажмите кнопку Начните, щелкните Все **программы,** нажмите кнопку Skype для бизнеса **2015,** а затем нажмите кнопку **Skype для бизнеса Server.**
    
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