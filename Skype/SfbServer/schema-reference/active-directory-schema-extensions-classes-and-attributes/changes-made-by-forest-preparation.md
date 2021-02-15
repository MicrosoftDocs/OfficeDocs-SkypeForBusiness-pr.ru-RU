---
title: Изменения, внесенные в ходе подготовки леса в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2e12613e-59f2-4810-a32d-24a9789a4a6e
description: В данном разделе описываются глобальные параметры и объекты, а также универсальные группы служб и административные группы, создаваемые на этапе подготовки леса.
ms.openlocfilehash: 4e8032cb91b012c710dc509708a813d55825f7a2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831919"
---
# <a name="changes-made-by-forest-preparation-in-skype-for-business-server"></a>Изменения, внесенные в ходе подготовки леса в Skype для бизнеса Server

В данном разделе описываются глобальные параметры и объекты, а также универсальные группы служб и административные группы, создаваемые на этапе подготовки леса.

## <a name="active-directory-global-settings-and-objects"></a>Глобальные параметры и объекты Active Directory

Если глобальные параметры хранятся в контейнере Configuration (как и для всех новых развертывании Skype для бизнеса Server), при подготовке леса используется существующий контейнер служб и добавляется объект **службы RTC** в объект Configuration\Services. В объект RTC Service процедура подготовки лета добавляет объект **Global Settings** типа msRTCSIP-GlobalContainer. Объект глобальных параметров содержит все параметры, которые применяются к развертыванию Skype для бизнеса Server. Если вы храните глобальные параметры в контейнере System, процедура подготовки леса использует контейнер Microsoft в контейнере System корневого домена и объект RTC Service в объекте System\Microsoft.

Процедура подготовки леса также добавляет новый объект **msRTCSIP-Domain** для корневого домена, в котором выполняется процедура.

## <a name="active-directory-universal-service-and-administration-groups"></a>Универсальные группы служб и административные группы Active Directory

Процедура подготовки леса создает универсальные группы на основании указанного вами домена и добавляет для этих групп элементы управления доступом (ACE). На данном этапе универсальные группы создаются в контейнерах User указанного вами домена.

Универсальные группы позволяют администраторам осуществлять доступ к глобальным параметрам и службам и управлять ими. Процедура подготовки леса добавляет следующие типы универсальных групп:

- **Административные группы** Эти группы определяют роли администратора для сети Skype для бизнеса Server.

- **Группы инфраструктуры** Эти группы предоставляют разрешения на доступ к определенным областям инфраструктуры Skype для бизнеса Server. Они выступают в качестве компонентов административных групп. Вам не следует изменять эти группы или добавлять пользователей непосредственно в них.

- **Группы служб** Эти группы — это учетные записи служб, необходимые для доступа к различным службам Skype для бизнеса Server.

В следующей таблице описываются административные группы.

**Административные группы, созданные во время подготовки леса**

|**Административная группа**|**Описание**|
|:-----|:-----|
|RTCUniversalServerAdmins  <br/> |Позволяет членам управлять параметрами серверов и пулов, включая все роли сервера, глобальные параметры и пользователей.  <br/> |
|RTCUniversalUserAdmins  <br/> |Позволяет членам управлять параметрами пользователей и перемещать пользователей из одного сервера или пула в другой.  <br/> |
|RTCUniversalReadOnlyAdmins  <br/> |Позволяет членам считывать параметры серверов, пулов и пользователей.  <br/> |

В следующей таблице описываются группы инфраструктуры.

**Группы инфраструктуры, созданные во время подготовки леса**

|**Группа инфраструктуры**|**Описание**|
|:-----|:-----|
|RTCUniversalGlobalWriteGroup  <br/> |Предоставляет доступ на запись к объектам глобальных параметров для Skype для бизнеса Server.  <br/> |
|RTCUniversalGlobalReadOnlyGroup  <br/> |Предоставляет доступ только для чтения к объектам глобальных параметров для Skype для бизнеса Server.  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Предоставляет доступ только для чтения к пользовательским настройкам Skype для бизнеса Server.  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Предоставляет доступ только для чтения к настройкам Skype для бизнеса Server. Данная группа не имеет доступа к параметрам уровня пулов, ей доступны только параметры для отдельного сервера.  <br/> |
|RTCUniversalSBATechnicians  <br/> |Предоставляет доступ только для чтения к конфигурации Skype для бизнеса Server и помещается в группу локальных администраторов устройств для survivable branch во время установки.  <br/> |

В следующей таблице описываются группы служб.

**Группы служб, созданные во время подготовки леса**

|**Группа служб**|**Описание**|
|:-----|:-----|
|RTCHSUniversalServices  <br/> |Включает учетные записи служб, используемые для запуска серверов переднего сервера и сервера Standard Edition. Эта группа позволяет серверам считывать и записывать доступ к глобальным настройкам Skype для бизнеса Server и объектам пользователей Active Directory.  <br/> |
|RTCComponentUniversalServices  <br/> |Включает учетные записи служб, используемые для запуска серверов A/V Conferencing Server, веб-служб, сервера-посредника, сервера архивации и сервера мониторинга.  <br/> |
|RTCProxyUniversalServices  <br/> |Включает учетные записи служб, используемые для запуска серверов Skype для бизнеса Server Edge Server.  <br/> |
|RTCUniversalConfigReplicator  <br/> |Включает серверы, которые могут участвовать в репликации центрального банка управления Skype для бизнеса Server.  <br/> |
|RTCSBAUniversalServices  <br/> |Предоставляет доступ только для чтения к настройкам Skype для бизнеса Server, но позволяет настраивать конфигурацию для установки сервера для survivable branch server и развертывания устройства для устройств для survivable branch appliance.  <br/> |

После этого процедура подготовки леса добавляет группы служб и административные группы в соответствующие группы инфраструктуры следующим образом:

- RTCUniversalServerAdmins добавляется в RTCUniversalGlobalReadOnlyGroup, RTCUniversalGlobalWriteGroup, RTCUniversalServerReadOnlyGroup и RTCUniversalUserReadOnlyGroup.

- RTCUniversalUserAdmins добавляется в качестве члена групп RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup и RTCUniversalUserReadOnlyGroup.

- RTCHSUniversalServices, RTCComponentUniversalServices и RTCUniversalReadOnlyAdmins добавляются в качестве членов групп RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup и RTCUniversalUserReadOnlyGroup.

Процедура подготовки леса также создает следующие группы управления доступом на основе ролей:

- CSAdministrator

- CSArchivingAdministrator

- CSHelpDesk

- CSLocationAdministrator

- CSResponseGroupAdministrator

- CSServerAdministrator

- CSUserAdministrator

- CSViewOnlyAdministrator

- CSVoiceAdministrator

- CsPersistentChatAdministator

- CsResponseGroupManager

Дополнительные сведения о ролях управления доступом на основе ролей и задачах, разрешенных для каждой из них, см. в разделе [Role-Based Access Control](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx) документации по планированию.

Процедура подготовки леса создает как частные, так и общие элементы управления доступом. Он создает частные AES в контейнере глобальных параметров, используемом Skype для бизнеса Server. Этот контейнер используется только Skype для бизнеса Server и расположен в контейнере Configuration или в контейнере System в корневом домене в зависимости от того, где хранятся глобальные параметры. В следующей таблице приведены общие элементы управления доступом, создаваемые процедурой подготовки леса.

**Общие элементы управления доступом, создаваемые процедурой подготовки леса**


| **ACE**                                                                 | **RTCUniversalGlobalReadOnlyGroup** |
|:------------------------------------------------------------------------|:------------------------------------|
| Чтение системного контейнера корневого домена (не унаследовано) **\\**\* <br/>        | X  <br/>                            |
| Чтение контейнера DisplaySpecifiers конфигурации (не наследуется)  <br/> | X  <br/>                            |

> [!NOTE]
> <strong>\\</strong>*AES, которые не наследуются, не предоставляет доступ к объектам-child в этих контейнерах. Наследуемые элементы управления доступом предоставляют доступ к дочерним объектам в таких контейнерах.

В контейнере Configuration в контексте именования Configuration процедура подготовки леса выполняет следующие задачи:

- Добавляет запись **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** для страницы **RTC property** в атрибутах adminContextMenu и adminPropertyPages описателя отображения языка для пользователей, контактов и InetOrgPersons (например, CN=user-Display,CN=409,CN=DisplaySpecifiers).

- Добавляет объект **RTCPropertySet** типа **controlAccessRight** в **Extended-Rights**, применяемый к классам User и Contact.

- Добавляет объект **RTCUserSearchPropertySet** типа **controlAccessRight** в **Extended-Rights**, применяемый к классам User, Contact, OU и DomainDNS.

- Добавляет **msRTCSIP-PrimaryUserAddress** в атрибут **extraColumns** каждого описателя отображения языкового подразделения (например, CN=organizationalUnit-Display,CN=409,CN=DisplaySpecifiers) и копирует значения атрибута **extraColumns** отображения по умолчанию (например, CN=default-Display, CN=409,CN=DisplaySpecifiers).

- Добавляет атрибуты фильтрации **msRTCSIP-PrimaryUserAddress**, **msRTCSIP-PrimaryHomeServer** и **msRTCSIP-UserEnabled** в атрибут **attributeDisplayNames** каждого описателя отображения языка для объектов Users, Contacts и InetOrgPerson (например, для английского: CN=user-Display,CN=409,CN=DisplaySpecifiers).


