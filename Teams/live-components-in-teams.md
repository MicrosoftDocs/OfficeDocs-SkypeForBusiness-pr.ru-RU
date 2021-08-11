---
title: Управление живыми компонентами в Teams
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: michalbr
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Узнайте, как управлять живыми компонентами в Teams.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: cb472822f7d55636bfd5ee4c48e7c962a705f6e05fd65b263952895040d69f7c
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54305021"
---
# <a name="manage-live-components-in-teams"></a>Управление живыми компонентами в Teams

Живые компоненты в Teams чате предлагают новый способ представления, создания и принятия решений вместе. Отправьте компонент, например таблицу, список задач или абзац, где каждый в чате может изменить свою линию и увидеть изменения по мере их внесения. Это означает, что вы можете собирать идеи и отзывы из своей команды, а также проводить меньше собраний и минимизируя потребность в длинных потоках чата.

**Выполнение задач быстрее.** Crowd-source agenda, track a group's action items, or take notes collectively. Это лишь несколько сценариев, облегчающих работу с живыми компонентами.

**Разделять компоненты.** В этом выпуске вы можете обмениваться живыми компонентами в различные Teams чаты. Получатели могут редактировать, где бы они ни находились, и мгновенно видеть обновления независимо от того, где были внесены изменения. В будущих выпусках живые компоненты будут поддерживаться в Teams и каналах, Outlook и в конечном итоге во всех Microsoft 365 приложениях.

**Начните в чате, создайте оттуда.** Каждый компонент, который Teams чате, автоматически сохранен в файл в OneDrive. Таким образом, вы можете начать совместную работу в чате, а затем перейти к файлу, где у вас больше визуального пространства для редактирования и можно добавить как можно больше компонентов, как вам нравится.

## <a name="clients-and-platforms"></a>Клиенты и платформы

Доступно в Teams приложениях на Windows, Mac, Linux, iOS и Android.

Начиная с начала сентября, живые компоненты будут доступны во всем мире. В конце сентября он будет доступен для облако сообщества для государственных организаций Mod (GCC).

## <a name="settings-management"></a>Параметры управления

Живые компоненты построены с поддержкой Microsoft Fluid Framework пакета Microsoft 365 и управляются из SharePoint Online, а не из центра администрирования Teams.

Вам потребуется последняя версия модуля [SharePoint PowerShell,](/office365/enterprise/powershell/manage-sharepoint-online-with-office-365-powershell) чтобы включить или отключить все опытом жидкости в Office 365 клиенте. Microsoft Fluid Framework по умолчанию **для всех** целевых клиентов выпуска. Так как живые компоненты предназначены для совместной работы, компоненты всегда делятся как редактируемые другими, даже если клиент настроен по умолчанию на просмотр только для других типов файлов. Дополнительные **сведения см. в** дополнительных сведениях по ссылке Дополнительные сведения см. в этой ссылке.

## <a name="checking-if-the-fluid-framework-is-enabled-through-the-sharepoint-online-powershell-cmdlet"></a>Проверка включения Fluid Framework веб-SharePoint PowerShell

1. [Подключение SharePoint PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps#to-connect-with-a-user-name-and-password). 

2. Проверьте, Fluid Framework включено, запуская Get-SPOTenant без каких-либо аргументов.

3. Убедитесь, что значение IsFluidEnabled **верно.**

## <a name="enabling-the-fluid-framework-through-the-sharepoint-online-powershell-cmdlet"></a>Включение Fluid Framework через SharePoint PowerShell 

1. [Подключение SharePoint PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps#to-connect-with-a-user-name-and-password). 

2. Включить fluid с помощью Set-SPOTenant -IsFluidEnabled $true 
   
   Изменение будет применяться в течение короткого времени в вашем аренде. 

Эта функция будет доступна на Teams Windows, Mac, iOS, Android. При включении пользователи увидят новый вариант вставки живых компонентов в текст сообщения для этих клиентов.

## <a name="disabling-fluid-framework-through-sharepoint-online-powershell-cmdlet"></a>Отключение Fluid Framework через SharePoint Веб-сайт PowerShell

1. [Подключение SharePoint PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).

2. Отключить жидкость с помощью Set-SPOTenant-Set-SPOTenant -IsFluidEnabled $false. 

   Изменение будет применяться в течение короткого времени в вашем аренде. 

Если вам необходимо повторно включить эту возможность, вы можете использовать SharePoint веб-SharePoint PowerShell.

```powershell
C:\\WINDOWS\\system32&gt; Connect-SPOService
cmdlet Connect-SPOService at command pipeline position 1

Supply values for the following parameters:
Url: <https://a830edad9050849822e21011208-admin.sharepoint.com/>
PS C:\\WINDOWS\\system32&gt; set-SPOTenant -isFluidEnabled $false
PS C:\\WINDOWS\\system32&gt;
```

## <a name="known-limitations"></a>Известные ограничения

- Создание таблицы или списка задач в качестве первого компонента после Teams перезапуска приложения может занять некоторое дополнительное время.

- Другие участники чата получат уведомление по электронной почте при упоминаний с символом at (@). (Уведомления at-mentions в Teams канале действий будут доступны в ближайшее время.)

- Поиск живых компонентов в Teams возвращает ссылку на компонент в office.com, а не на само сообщение чата.

- Живые компоненты отключены в федерабельных чатах и включены для регулярных чатов с гостевой учетной записью с помощью Azure B2B.

- Хотя вы можете обмениваться компонентом в Teams каналах и других Microsoft 365 приложениях, получатели получают ссылку в большинстве мест в это время. В будущем планируется редактирование в режиме inline для получения дополнительных опытом.

## <a name="storage-of-fluid-files"></a>служба хранилища `.fluid` файлов

**Как `.fluid` хранятся?**

Живые компоненты, созданные в Teams, хранятся в файле, храняном в `.fluid` OneDrive для бизнеса. Быть файлом в OneDrive для бизнеса означает, что пользователи могут создавать, открывать и управлять живыми компонентами (файлами) так же легко, как и `.fluid` любой Office документ.

Пользователи могут искать контент в файлах `.fluid` из Office.com и OneDrive для бизнеса.
`.fluid` файлы работают с функциями управления данными, например с функцией eDiscovery, auditing, reporting и legal hold.

`.fluid`теперь файлы будут отображаться на Office.com и OneDrive для бизнеса, например в последних и рекомендуемых областях.
`.fluid`файлы могут быть восстановлены в предыдущих версиях из OneDrive для бизнеса.

Участники чата должны иметь OneDrive учетную запись для создания живых компонентов. Без допустимой OneDrive учетной записи участники чата по-прежнему могут сотрудничать с компонентом, созданным другими пользователями, которые имеют допустимую OneDrive учетную запись, но не могут создать свою собственную.

[Перемещение](https://support.microsoft.com/en-us/office/move-files-and-folders-between-onedrive-and-sharepoint-5916f90d-f58a-4bf9-b135-10853f516d0b) файла с OneDrive на веб-SharePoint приведет к невозможной загрузке живого компонента `.fluid` в Teams чате.

**Что произойдет, если владелец файла покинет компанию?**

[OneDrive политики хранения](/microsoft-365/compliance/retention-policies-sharepoint?view=o365-worldwide#when-a-user-leaves-the-organization) применяются к файлам так же, как и к другому контенту, `.fluid` созданному пользователем.

**Как `.fluid` делятся файлы?**

Живые компоненты можно вставить в Teams или скопировать из одного чата в другой. (Живые компоненты еще не поддерживаются в каналах.) Они по умолчанию имеют существующие разрешения клиента, но пользователи могут изменить разрешения перед отправкой, чтобы убедиться, что у каждого есть доступ.

Открытие компонентов из Teams чата в Office.com предоставляет функции общего доступа в верхней части окна, аналогичные вариантам совместного доступа, предлагаемым для других Office документов.

**Что делать, `.fluid` если файл поврежден или поврежден?**

История версий позволяет просмотреть и скопировать из предыдущих версий файла.

**Какие приложения могут открывать и изменять `.fluid` файлы?**

`.fluid`файлы могут открываться только в качестве ссылок в браузере, например Office.com, а также в качестве живых компонентов в Teams чате. При загрузке их нельзя открыть снова, не загрузив их обратно в OneDrive для бизнеса или SharePoint Online.
