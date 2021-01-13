---
title: Настройка политик голосовой почты, записей использования PSTN и маршрутов голосовых вызовов в Skype для бизнеса
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
ms.assetid: 1e5a15f9-6f42-4dc6-baaa-24daf54afc4d
description: Сводка. Узнайте, как настроить политики голосовой почты, записи использования ЗВОНКОВ и маршруты голосовых вызовов в Skype для бизнеса Server.
ms.openlocfilehash: f8c9f75f24a06b210a1c17ed11a1485ab5158f3d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830451"
---
# <a name="configure-voice-policies-pstn-usage-records-and-voice-routes-in-skype-for-business"></a>Настройка политик голосовой почты, записей использования PSTN и маршрутов голосовых вызовов в Skype для бизнеса
 
**Сводка:** Learn how to configure voice policies, PSTN usage records, and voice routes in Skype for Business Server.
  
Политики голосовой связи, записи использования ТСОП и маршруты голосовых вызовов тесно связаны. Вы настраиваете политики голосовой связи, выбирая набор возможностей звонков и назначая политике набор записей использования ТСОП, указывающих, какие права разрешены для пользователей или групп, которым назначена политика голосовой связи. Маршрутам голосовых вызовов также назначаются записи использования ТСОП, служащие для сопоставления маршрутов с пользователями, которым разрешено эти маршруты использовать. Таким образом, пользователи могут выполнять только звонки, использующие маршруты, для которых имеется соответствующая запись использования ТСОП.
  
Рекомендуемый рабочий процесс для нового развертывания корпоративной голосовой связи заключается в том, чтобы начать с настройки политики голосовой связи, включающей в себя подходящие записи использования ТСОП, а затем сопоставить соответствующие маршруты с каждой из записей использования ТСОП. 
  
> [!NOTE]
> Вы также можете создать политики голосовой связи с  *областью*  действия пользователя и назначить их отдельным пользователям или группам.
  
Подробные сведения о выполнении каждой из этих задач см. процедуры, приведенные в данном разделе.
  
## <a name="in-this-section"></a>В этом разделе:

- [Create or modify a voice policy and configure PSTN usage records in Skype for Business](voice-policy-and-pstn-usage-records.md)
    
- [Настройка escape-сообщения голосовой почты в Skype для бизнеса](configure-voice-mail-escape.md)
    
- [Просмотр записей использования PSTN в Skype для бизнеса](view-pstn-usage-records.md)
    
- [Создание или изменение маршрута голосовой почты в Skype для бизнеса](create-or-modify-a-voice-route.md)
    
- [Экспорт или импорт файла конфигурации маршрута голосовых вызовов в Skype для бизнеса](voice-route-configuration-import-export.md)
    
- [Публикация ожидающих изменений в конфигурации маршрутации голосовой почты в Skype для бизнеса](voice-route-config-changes.md)
    

