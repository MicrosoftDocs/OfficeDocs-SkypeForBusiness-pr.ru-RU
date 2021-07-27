---
title: Вывод из эксплуатации Skype для бизнеса Server
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
ms.openlocfilehash: bdd38578d8ee98c26e6515c1cd4baa0ef8a825cf
ms.sourcegitcommit: 9879bc587382755d9a5cd63a75b0e7dc4e15574c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/21/2021
ms.locfileid: "53510790"
---
# <a name="remove-your-on-premises-skype-for-business-deployment"></a>Удаление локального развертывания Skype для бизнеса

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

В этой статье описывается, как удалить локальное развертывание Skype для бизнеса развертывания. Это шаг 4 из следующих действий по выводу из эксплуатации локальной среды:

- Этап 1. [Перемещение всех необходимых пользователей из локального в интернет.](decommission-move-on-prem-users.md) 

- Этап 2. [Отключите гибридную конфигурацию.](cloud-consolidation-disabling-hybrid.md)

- Этап 3. [Перенос конечных точек гибридных приложений из локального в online](decommission-move-on-prem-endpoints.md)

- **Шаг 4. Удалите локальное развертывание Skype для бизнеса развертывания.** (В этой статье)


> [!IMPORTANT] 
> Действия, описанные в этой статье, применяются только в том случае, если метод 2 используется для управления атрибутами пользователей, как [описано здесь.](cloud-consolidation-managing-attributes.md#method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory) Если используется метод 1, не используйте описанные в этой статье действия для удаления Skype для бизнеса серверов. Вместо этого вы можете повторно образ серверов.

Для выполнения действий в этой статье необходимы привилегии как для группы администраторов схемы, так и для Enterprise администратора. Эти привилегии необходимы для отмены Skype для бизнеса Server схемы и изменений на уровне лесов в службы домена Active Directory. Вы также должны быть членом группы RTCUniversalServerAdmins.


## <a name="prepare-to-remove-the-skype-for-business-deployment"></a>Подготовка к удалению Skype для бизнеса развертывания

После перемещения всех необходимых учетных записей пользователей в облако могут по-прежнему оставаться некоторые локального объекта, такие как контакты и приложения, которые необходимо очистить.

Чтобы очистить эти объекты, используйте указанные ниже шаги и убедитесь, что вы входите в группу локального администратора и группу RTCUniversalServerAdmins. Обратите внимание, что ExUmContacts и PersistantChatEndPoints недоступны в Skype для бизнеса Server 2019 г. Если у вас Skype для бизнеса Server 2019 г., соответствующие cmdlets в шагах ниже должны быть опущены.

1. Чтобы проверить, есть ли контакты или приложения, связанные с развертыванием Skype для бизнеса Server локального развертывания, запустите следующие Skype для бизнеса Server PowerShell.

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
2. Просмотрите списки выходных данных из списков в шаге 1. Затем, если объекты можно удалить, запустите следующие Skype для бизнеса Server PowerShell:

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

1. Логически удалите развертывание Skype для бизнеса Server, за исключением одного переднего конца, следующим образом:

   1. Обновите Skype для бизнеса Server топологии, чтобы иметь единый пул переднего входа:

      1. В Topology Builder скачайте новую копию и перейдите в пул Frontend.
      1. Щелкните пул правой кнопкой мыши и выберите команду **Изменить свойства**.
      1. В **Associations** отойдите от пула **ассоциированных элементов** (для компонентов мультимедиа) и нажмите **кнопку ОК**.
      1. Если имеется несколько пулов frontend, удалите ассоциации для всех остальных пулов.
      1. Выберите **действие > удаление развертывания**.
      1. Выберите **действие > Опубликовать топологию**.

    1. После публикации топологии выполните дополнительные действия, описанные в мастере.

2. Удалите Skype для бизнеса Server конференций, заняв следующий Skype для бизнеса Server PowerShell:

   ```PowerShell
   Get-CsConferenceDirectory | Remove-CsConferenceDirectory -Force
   ```

3. Завершите развертывание Skype для бизнеса Server развертывания с помощью следующего Skype для бизнеса Server PowerShell:

   ```PowerShell
   Publish-CsTopology -FinalizeUninstall
   ```
   > [!NOTE]
   > Если на этом шаге возвращается ошибка, откройте билет поддержки Майкрософт, чтобы получить помощь в удалении оставшихся устаревших объектов.

4. Удалите пункт управления службами Центра управления магазином, заняв следующий Skype для бизнеса Server PowerShell:

   ```PowerShell
   Remove-CsConfigurationStoreLocation
   ``` 

5. Отмена Skype для бизнеса Server на уровне домена Active Directory при запуске следующего Skype для бизнеса Server PowerShell:

   ```PowerShell
   Disable-CsAdDomain
   ```
6. Отменять Skype для бизнеса Server изменения уровня леса Active Directory, выполнив следующий Skype для бизнеса Server PowerShell:

   ```PowerShell
   Disable-CsAdForest
   ```

## <a name="see-also"></a>См. также

- [Прекращение использования локальной среды Skype для бизнеса](decommission-on-prem-overview.md)

- [Перемещение всех необходимых пользователей из локальной сети в интернет](decommission-move-on-prem-users.md)

- [Отключение гибридной конфигурации](cloud-consolidation-disabling-hybrid.md)

- [Перемещение конечных точек гибридного приложения из локального в online](decommission-move-on-prem-endpoints.md)

