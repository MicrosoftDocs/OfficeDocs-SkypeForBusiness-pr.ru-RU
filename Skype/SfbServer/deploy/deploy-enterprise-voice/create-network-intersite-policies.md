---
title: Создание сетевого политик межсайтового взаимодействия в Скайп для Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b0714aae-55dc-4587-b718-34a03f596b22
description: Создание политики между сайтами, которые используются с корпоративной голосовой связи контроля допуска звонков в Скайп для Business Server.
ms.openlocfilehash: 6619787bf071afe719c715de39e23b992d6e6ede
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30880160"
---
# <a name="create-network-intersite-policies-in-skype-for-business-server"></a>Создание сетевого политик межсайтового взаимодействия в Скайп для Business Server
 
Создание политики между сайтами, которые используются с корпоративной голосовой связи контроля допуска звонков в Скайп для Business Server. 
  
Межсайтовая сетевая политика определяет ограничения пропускной способности между сайтами, соединенными прямыми каналами связи по глобальной сети.
  
> [!IMPORTANT]
> Сетевая межсайтовая политика является обязательным *только* при наличии прямое соединение между двумя сетевыми узлами.
  
В примере топологии для Северной Америки показано прямое соединение между узлами Reno (г. Рино) и Albuquerque (г. Альбукерке). Этим двум узлам требуется межузловая политика, которая применяет соответствующий профиль политики пропускной способности. В следующем примере показано применение профиля 20Mb_Link.
  
### <a name="to-create-a-network-inter-site-policy"></a>Создание межсайтовой сетевой политики

1. Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.
    
2. Чтобы создать межсайтовые сетевые политики и применить соответствующий профиль политики пропускной способности для двух узлов с прямым соединением, выполните командлет New-CsNetworkInterSitePolicy. Пример:
    
   ```
   New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link
   ```

3. Повторите шаг 2 для всех пар сетевых узлов, имеющих прямое соединение.
    
## <a name="see-also"></a>См. также

[New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps)
  
[Get-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/get-csnetworkintersitepolicy?view=skype-ps)
  
[Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/set-csnetworkintersitepolicy?view=skype-ps)
  
[Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkintersitepolicy?view=skype-ps)
