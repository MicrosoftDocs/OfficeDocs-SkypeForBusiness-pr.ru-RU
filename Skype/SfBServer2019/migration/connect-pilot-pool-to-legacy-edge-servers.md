---
title: Подключение пилотного пула к старым пограничным серверам
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: After deploying Skype for Business Server 2019, you need to configure a federation route for your site. Чтобы использовать федераированный маршрут, используемый устаревшей установкой, необходимо настроить Skype для бизнеса Server 2019 на использование этого маршрута.
ms.openlocfilehash: 8243ebbf9540587dedd8e4ae3a51e22f9a315728
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753929"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a>Подключение пилотного пула к старым пограничным серверам

After deploying Skype for Business Server 2019, you need to configure a federation route for your site. Чтобы использовать федераированный маршрут, используемый устаревшей установкой, необходимо настроить Skype для бизнеса Server 2019 на использование этого маршрута. 
  
Чтобы позволить сайту Skype для бизнеса Server 2019 использовать директор и edge-сервер устаревшего развертывания, используйте построитель топологий для связывание устаревшего пула.
  
### <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a>Связь устаревшего пограничного пула с помощью построителя топологий

1. Откройте построитель топологий. 
    
2. Выберите свой сайт, который находится непосредственно под узлом **Skype для бизнеса Server.** 
    
3. В меню **Actions** (Действия) выберите команду **Изменить свойства**.
    
4. В левой области выберите **Федеративный маршрут**.
    
5. В **области назначения маршрута** федерации сайта выберите "Включить **федерацию SIP",** а затем выберите устаревший директор или устаревший сервер, если директор не указан.
  
6. Нажмите кнопку **ОК**, чтобы закрыть страницу **изменения свойств**. 
    
7. In Topology Builder, under the Skype for Business Server 2019 node, navigate to the **Standard Edition server** or Enterprise Edition Front End **pools,** right-click the pool, and then click **Edit Properties**.
    
8. В разделе **Associations** (Связи) установите флажок **Associate Edge pool (for media components)** (Связать пограничный пул (для компонентов медиа)). 
    
9. Выберите в списке устаревший пограничный сервер. 
  
10. Нажмите кнопку **ОК**, чтобы закрыть страницу **изменения свойств**. 
    
11. In **Topology Builder**, select the top-most node, **Skype for Business Server**.
    
12. В меню **Action** (Действие) выберите команду **Publish Topology** (Опубликовать топологию) и нажмите кнопку **Далее**.
    
13. Когда **мастер публикации** завершит работу, нажмите кнопку **Готово**.
    

