---
title: Создание сетевых политик межсайтов в Skype для бизнеса Server
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
description: Создайте сетевые политики межсайтов, которые используются Корпоративная голосовая связь контроля допуска звонков в Skype для бизнеса Server.
ms.openlocfilehash: 69609da75fdfa87309743920eace59892a440f2b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822479"
---
# <a name="create-network-intersite-policies-in-skype-for-business-server"></a>Создание сетевых политик межсайтов в Skype для бизнеса Server
 
Создайте сетевые политики межсайтов, которые используются Корпоративная голосовая связь контроля допуска звонков в Skype для бизнеса Server. 
  
Политика межсайтовой сети определяет ограничения пропускной способности между сайтами, которые имеют прямые связи WAN между ними.
  
> [!IMPORTANT]
> Сетовая межсайтовая политика необходима, только если между двумя сетевыми узлами существует прямая межсайтовая связь. 
  
В примере топологии "Северная Америка" имеется прямая связь между сайтами Reno и Albuquerque. Для этих двух сайтов требуется межсайтовая политика, которая применяет соответствующий профиль политики пропускной способности. В следующем примере применяется 20Mb_Link профиля.
  
### <a name="to-create-a-network-inter-site-policy"></a>Создание сетевой политики межсайтов

1. Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**
    
2. Запустите New-CsNetworkInterSitePolicy, чтобы создать сетевые межсайтовую политику и применить соответствующий профиль политики пропускной способности для двух сайтов с прямым перекрестным соединением. Например, выполните команду:
    
   ```powershell
   New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link
   ```

3. Повторите шаг 2 по мере необходимости, чтобы создать сетевые политики межсайтов для всех пар сетевых сайтов с прямым перекрестным соединением.
    
## <a name="see-also"></a>См. также

[New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps)
  
[Get-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/get-csnetworkintersitepolicy?view=skype-ps)
  
[Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/set-csnetworkintersitepolicy?view=skype-ps)
  
[Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkintersitepolicy?view=skype-ps)
