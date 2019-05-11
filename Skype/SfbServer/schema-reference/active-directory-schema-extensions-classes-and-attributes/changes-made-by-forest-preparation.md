---
title: Изменения, внесенные с подготовки леса в Скайп для Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2e12613e-59f2-4810-a32d-24a9789a4a6e
description: В этом разделе описываются глобальные параметры и объекты и универсальные группы служб и административные, создаваемые на этапе подготовки леса.
ms.openlocfilehash: de5171887d84e3d3d5d835d6bb59af24fcb5820d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33907129"
---
# <a name="changes-made-by-forest-preparation-in-skype-for-business-server"></a>Изменения, внесенные с подготовки леса в Скайп для Business Server

В этом разделе описываются глобальные параметры и объекты и универсальные группы служб и административные, создаваемые на этапе подготовки леса.

## <a name="active-directory-global-settings-and-objects"></a>Глобальные параметры Active Directory и объекты

Если хранения глобальных параметров в контейнере конфигурации (как в случае для всех новых Скайп для развертываний Business Server), использует существующий контейнер служб и добавляет объект **Службы RTC** в разделе Configuration\Services подготовки леса объект. В разделе объекте службы RTC подготовки леса добавляет объект **Глобальные параметры** типа msRTCSIP-GlobalContainer. Объект global settings содержит все параметры, применимые к Скайп для развертывания Business Server. При сохранении глобальных параметров в контейнере System подготовки леса использует контейнер Microsoft в разделе контейнера System корневого домена и объект службы RTC в объекте System\Microsoft.

Процедура подготовки леса также добавляет новый объект **msRTCSIP-Domain** для корневого домена, в котором выполняется процедура.

## <a name="active-directory-universal-service-and-administration-groups"></a>Active Directory универсальные группы служб и административные группы

Подготовка леса создает универсальных групп на основе домена, который указан и добавляет записи управления доступом (ACE) для этих групп. На этом этапе создается универсальных групп в контейнерах пользователя домена, который указан.

Универсальные группы позволяют администраторам доступ и управлять глобальные параметры и службы. Процедура подготовки леса добавляет следующие типы универсальных групп:

- **Административные группы** Эти группы определения ролей администратора для Скайп для сети Business Server.

- **Группы инфраструктуры** Эти группы предоставить разрешения на доступ к конкретной части Скайп для инфраструктуры Business Server. Они работают как компоненты административные группы. Не следует изменять эти группы или добавлять пользователей непосредственно к ним.

- **Группы служб** Эти группы — это учетные записи служб, которые необходимы для доступа к различным Скайп для служб Business Server.

В следующей таблице описываются административные группы.

**Административные группы, созданные во время подготовки леса**

|**Административная группа**|**Описание**|
|:-----|:-----|
|RTCUniversalServerAdmins  <br/> |Позволяет членам управлять сервера и параметров пула, в том числе всех ролей сервера, глобальные параметры и пользователей.  <br/> |
|RTCUniversalUserAdmins  <br/> |Позволяет членам управлять параметрами пользователей и перемещение пользователей из одного сервера или пула в другой.  <br/> |
|RTCUniversalReadOnlyAdmins  <br/> |Позволяет членам считывать параметры серверов, пулов и пользователей.  <br/> |

В следующей таблице описываются группы инфраструктуры.

**Группы инфраструктуры, созданные во время подготовки леса**

|**Группа инфраструктуры**|**Описание**|
|:-----|:-----|
|RTCUniversalGlobalWriteGroup  <br/> |Предоставляет доступ на запись к объектам глобальных параметров для Скайп для Business Server.  <br/> |
|Групп RTCUniversalGlobalReadOnlyGroup  <br/> |Предоставляет доступ только для чтения к объектам глобальных параметров для Скайп для Business Server.  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Предоставляет доступ только для чтения к Скайп для параметров пользователя Business Server.  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Предоставляет доступ только для чтения к Скайп для параметров Business Server. Эта группа не имеет доступа к параметрам уровня пула, только для параметров, относящихся к отдельному серверу.  <br/> |
|RTCUniversalSBATechnicians  <br/> |Предоставляет доступ только для чтения к Скайп для конфигурации Business Server и помещается в группу локальных администраторов устройств для обеспечения связи в филиалах во время установки.  <br/> |

В следующей таблице описываются группы службы.

**Группы служб, созданные во время подготовки леса**

|**Группа служб**|**Описание**|
|:-----|:-----|
|RTCHSUniversalServices  <br/> |Включает в себя учетные записи служб, используемые для работы сервера переднего плана и серверов Standard Edition. Эту группу разрешает доступ чтение и запись серверы Скайп для глобальных параметров Business Server и объектов-пользователей Active Directory.  <br/> |
|RTCComponentUniversalServices  <br/> |Включает в себя учетные записи служб, используемые для работы и видео конференций, веб-служб, сервера-посредника, сервера архивации и мониторинга сервера.  <br/> |
|RTCProxyUniversalServices  <br/> |Включает в себя службы учетные записи, используемые для запуска Скайп для пограничных серверов Business Server.  <br/> |
|RTCUniversalConfigReplicator  <br/> |Включает в себя серверы, которые могут принимать участие в Скайп репликации хранилища централизованного управления Business Server.  <br/> |
|RTCSBAUniversalServices  <br/> |Предоставляет доступ только для чтения к Скайп для параметров Business Server, но обеспечивает настройку для установки сервера обеспечения связи в филиалах и развертывания устройство для обеспечения связи в филиалах.  <br/> |

Процедура подготовки леса добавляет группы служб и административные группы в соответствующие группы инфраструктуры следующим образом:

- RTCUniversalServerAdmins добавляется групп RTCUniversalGlobalReadOnlyGroup, RTCUniversalGlobalWriteGroup, RTCUniversalServerReadOnlyGroup и RTCUniversalUserReadOnlyGroup.

- RTCUniversalUserAdmins добавляется в качестве члена групп RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup и RTCUniversalUserReadOnlyGroup.

- RTCHSUniversalServices, RTCComponentUniversalServices и RTCUniversalReadOnlyAdmins добавляются в качестве членов групп RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup и RTCUniversalUserReadOnlyGroup.

Процедура подготовки леса также создает следующие группы управления ДОСТУПОМ на основе ролей доступ:

- CSAdministrator

- Роли CSArchivingAdministrator

- CSHelpDesk

- CSLocationAdministrator

- CSResponseGroupAdministrator

- CSServerAdministrator

- CSUserAdministrator

- CSViewOnlyAdministrator

- CSVoiceAdministrator

- CsPersistentChatAdministator

- CsResponseGroupManager

Для получения дополнительных сведений о ролях RBAC и разрешенные для каждой задачи содержатся в документации по планированию [управления доступом на основе ролей](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx) .

Подготовка леса создает частной и общедоступной элементы управления доступом. Он создает частных элементов ACE для контейнера глобальные параметры, используемые Скайп для Business Server. Этот контейнер используется только Скайп для Business Server и расположен в контейнере конфигурации или контейнера System корневого домена, в зависимости от того, где хранятся глобальные параметры. В следующей таблице перечислены общие элементы управления доступом, созданные подготовки леса.

**Общие элементы управления доступом, созданные подготовки леса**


| **ЭЛЕМЕНТ УПРАВЛЕНИЯ ДОСТУПОМ**                                                                 | **Групп RTCUniversalGlobalReadOnlyGroup** |
|:------------------------------------------------------------------------|:------------------------------------|
| Чтение контейнера System (не наследуется) корневого домена**\\**\* <br/>        | X  <br/>                            |
| Контейнера DisplaySpecifiers конфигурации чтения (не наследуется)  <br/> | X  <br/>                            |

> [!NOTE]
> <strong>\\</strong>* Записи ACE, которые не наследуются предоставляет доступ к дочерним объектам в разделе этих контейнеров. Записи ACE, наследуемые предоставить доступ к дочерним объектам в разделе этих контейнеров.

В контейнере Configuration в контексте именования Configuration процедура подготовки леса выполняет следующие задачи:

- Добавляет запись **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** для страницы **RTC свойства** в разделе adminContextMenu и adminPropertyPages атрибуты языка отображения описателя для пользователей, контактов и InetOrgPersons (например, CN = User-Display, CN = 409, CN = DisplaySpecifiers).

- Добавляет объект **RTCPropertySet** типа **controlAccessRight** в **Extended-Rights** , применяемый к классам User и Contact.

- Добавляет объект **RTCUserSearchPropertySet** типа **controlAccessRight** в **Extended-Rights** , которая применяется для пользователей, контактов, OU и DomainDNS классы.

- Добавляет **msRTCSIP-PrimaryUserAddress** в атрибут **extraColumns** каждого описателя отображения языкового подразделения (OU) (например, CN = organizationalUnit-Display, CN = 409, CN = DisplaySpecifiers) и копирует значения атрибут **extraColumns** отображения по умолчанию (например, CN = default-Display, CN = 409, CN = DisplaySpecifiers).

- Добавляет **msRTCSIP-PrimaryUserAddress**, **msRTCSIP-PrimaryHomeServer**и **msRTCSIP-UserEnabled** фильтрации атрибуты в атрибут **attributeDisplayNames** каждого языка отображения описателя для пользователей, контактов, и объектов InetOrgPerson (например, на английском языке: CN = user-Display, CN = 409, CN = DisplaySpecifiers).


