---
title: Списание Skype для бизнеса Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Инструкции по выводу из эксплуатации Skype для бизнеса Server.
ms.openlocfilehash: 9c6051a07fc05297985b3692351c36791d8842bb
ms.sourcegitcommit: 71d90f0a0056f7604109f64e9722c80cf0eda47d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2021
ms.locfileid: "51656695"
---
# <a name="remove-your-on-premises-skype-for-business-deployment"></a>Удаление локального развертывания Skype для бизнеса

В этой статье описывается, как удалить локальное развертывание Skype для бизнеса. Это шаг 4 из следующих действий по выводу из эксплуатации локальной среды:

- Этап 1. [Перемещение всех необходимых пользователей из локального в интернет.](decommission-move-on-prem-users.md) 

- Шаг 2. [Отключите гибридную конфигурацию.](cloud-consolidation-disabling-hybrid.md)

- Шаг 3. [Перемещение конечных точек гибридного приложения из локального в online](decommission-move-on-prem-endpoints.md)

- **Шаг 4. Удалите локальное развертывание Skype для бизнеса.** (В этой статье)


> [!IMPORTANT] 
> Действия, описанные в этой статье, применяются только в том случае, если метод 2 используется для управления атрибутами пользователей, как [описано здесь.](cloud-consolidation-disabling-hybrid.md#method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory) Если используется метод 1, не используйте описанные в этой статье действия для удаления серверов Skype для бизнеса. Вместо этого вы можете повторно образ серверов.

Для выполнения действий в этой статье необходимы привилегии как для группы администраторов схемы, так и для группы корпоративного администратора. Эти привилегии необходимы для отмены схемы Skype для бизнес-сервера и изменения уровня леса в службы домена Active Directory. Вы также должны быть членом группы RTCUniversalServerAdmins.


## <a name="prepare-to-remove-the-skype-for-business-deployment"></a>Подготовка к удалению развертывания Skype для бизнеса

После перемещения всех необходимых учетных записей пользователей в облако могут по-прежнему оставаться некоторые локального объекта, такие как контакты и приложения, которые необходимо очистить.

Чтобы очистить эти объекты, используйте указанные ниже шаги и убедитесь, что вы входите в группу локального администратора и группу RTCUniversalServerAdmins. Обратите внимание, что ExUmContacts и PersistantChatEndPoints недоступны в Skype для бизнеса Server 2019. Если у вас есть Skype для бизнеса Server 2019, соответствующие cmdlets в шагах ниже должны быть опущены.

1. Чтобы проверить, есть ли какие-либо контакты или приложения, связанные с локальной развертыванием Skype для бизнеса Server, запустите следующие cmdlets Skype для бизнеса Server PowerShell.

   ```PowerShell
   Get-CsMeetingRoom
   Get-CsCommonAreaPhone
   Get-CsAnalogDevice
   Get-CsExUmContact
   Get-CsDialInConferencingAccessNumber
   Get-CsRgsWorkflow
   Get-CsTrustedApplicationEndpoint
   Get-CsTrustedApplication
   Get-CsPersistentChatEndpoint
   Get-CsAudioTestServiceApplication
   Get-CsCallParkOrbit
   ```
2. Просмотрите списки выходных данных из списков в шаге 1. Затем, если объекты можно удалить, запустите следующие кодлеты Skype для бизнеса Server PowerShell:

   ```PowerShell
   Get-CsMeetingRoom | Disable-CsMeetingRoom
   Get-CsCommonAreaPhone | Remove-CsCommonAreaPhone 
   Get-CsAnalogDevice | Remove-CsAnalogDevice
   Get-CsExUmContact | Remove-CsExUmContact
   Get-CsDialInConferencingAccessNumber | Remove-CsDialInConferencingAccessNumber
   Get-CsRgsWorkflow | Remove-CsRgsWorkflow
   Get-CsTrustedApplicationEndpoint | Remove-CsTrustedApplicationEndpoint
   Get-CsTrustedApplication | Remove-CsTrustedApplication -Force
   Get-CsPersistentChatEndpoint |  Remove-CsPersistentChatEndpoint
   Get-CsCallParkOrbit | Remove-CsCallParkOrbit -Force
   Get-CsVoiceRoute | Remove-CsVoiceRoute -Force
   ```
## <a name="remove-your-on-premises-skype-for-business-deployment"></a>Удаление локального развертывания Skype для бизнеса

После выполнения всех предварительных действий можно удалить развертывание Skype для бизнеса, следуя следующим шагам:

1. Логически удалите развертывание Skype для бизнес-сервера, за исключением одного переднего конца, следующим образом:

   а. Обновите топологию Skype для бизнес-сервера, чтобы иметь единый пул переднего входа:

     - В Topology Builder скачайте новую копию и перейдите в пул Frontend.
     - Щелкните пул правой кнопкой мыши и выберите команду **Изменить свойства**.
     - В **Associations** отойдите от пула **ассоциированных элементов** (для компонентов мультимедиа) и нажмите **кнопку ОК**.
     - Если имеется несколько пулов frontend, удалите ассоциации для всех остальных пулов.
     - Выберите **действие > удаление развертывания**.
     - Выберите **действие > Опубликовать топологию**.

    б. После публикации топологии выполните дополнительные действия, описанные в мастере.

2. Удалите каталоги конференций Skype для бизнеса Server, заняв следующий кодлет Skype для бизнеса Server PowerShell:

   ```PowerShell
   Get-CsConferenceDirectory | Remove-CsConferenceDirectory -Force
   ```

3. Завершите развертывание Skype для бизнес-сервера, заняв следующий код Skype для бизнеса Server PowerShell:

   ```PowerShell
   Publish-CsTopology -FinalizeUninstall
   ```
   > [!NOTE]
   > Если на этом шаге возвращается ошибка, откройте билет поддержки Майкрософт, чтобы получить помощь в удалении оставшихся устаревших объектов.

4. Удалите пункт управления централизованным хранилищем обслуживания, заняв следующий код Skype для бизнес-сервера PowerShell:

   ```PowerShell
   Remove-CsConfigurationStoreLocation
   ``` 

5. Отменять изменения лесного уровня домена Skype для бизнеса Server Active Directory, запуская следующий комдлет Skype для бизнеса Server PowerShell:

   ```PowerShell
   Disable-CsAdDomain
   ```
6. Отмена схемы домена Skype для бизнеса Server Active Directory изменяется при запуске следующего cmdlet Skype для бизнеса Server PowerShell:

   ```PowerShell
   Disable-CsAdForest
   ```

## <a name="see-also"></a>См. также

- [Прекращение использования локальной среды Skype для бизнеса](decommission-on-prem-overview.md)

- [Перемещение всех необходимых пользователей из локальной сети в интернет](decommission-move-on-prem-users.md)

- [Отключение гибридной конфигурации](cloud-consolidation-disabling-hybrid.md)

- [Перемещение конечных точек гибридного приложения из локального в online](decommission-move-on-prem-endpoints.md)











