---
title: Управление компонентами в Teams
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: michalbr
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Узнайте, как управлять компонентами в Teams.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 031f49d79659e0d5af1152e054466255d208a146
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58631463"
---
# <a name="manage-live-components-in-teams"></a>Управление компонентами в Teams

Компоненты в Teams чате предоставляют новый способ идеи, создания и принятия решений вместе. Отправьте компонент, например таблицу, список задач или абзац, где все в чате могут редактировать текст и видеть изменения по мере их внесения. Это означает, что вы можете собирать идеи и отзывы от своей команды, проводить меньше собраний и свести к минимуму потребность в длинных беседах чата.

**Вы можете быстрее выполнять задачи вместе.** Личные вопросы, отслеживание действий группы или совместное заметок. Это лишь несколько сценариев, упрощающих работу с компонентами в прямом эфире.

**"Поделиться компонентами".** В этом выпуске вы можете делиться компонентами в Teams чатах. Получатели могут редактировать сообщения, где бы они ни находились, и сразу же видеть обновления независимо от того, где были внесены изменения. В будущих выпусках компоненты будут поддерживаться в Teams заметок к собраниям и каналам, Outlook, а в конечном итоге во Microsoft 365 приложениях.

**Начните в чате, создайте оттуда.** Каждый компонент, который вы Teams чате, автоматически сохраняются в файле в OneDrive. Таким образом, вы можете приступить к совместной работы в чате, а затем перейти к файлу, где у вас есть больше места для редактирования и вы можете добавить нужное количество компонентов.

## <a name="clients-and-platforms"></a>Клиенты и платформы

Доступно в Teams на Windows, Mac, Linux, iOS и Android.

С начала сентября живые компоненты будут доступны глобально. В конце сентября она будет доступна для облако сообщества для государственных организаций Mod (GCC).

## <a name="settings-management"></a>Параметры управления

Компоненты в режиме Microsoft Fluid Framework поддерживаются во Microsoft 365 и управляются из SharePoint Online, а не из центра Teams администрирования.

Вам потребуется последняя версия модуля [SharePoint Online PowerShell,](/office365/enterprise/powershell/manage-sharepoint-online-with-office-365-powershell) чтобы включить или отключить все плавные возможности в Office 365 клиента. Microsoft Fluid Framework для всех целевых клиентов выпусков по умолчанию в режиме ON.  Так как живые компоненты предназначены для совместной работы, они всегда совместно редактируемые другими людьми, даже если в вашем клиенте по умолчанию настроено представление только для других типов файлов. Дополнительные **сведения см.** в ссылке Дополнительные сведения рядом с параметром.

## <a name="checking-if-the-fluid-framework-is-enabled-through-the-sharepoint-online-powershell-cmdlet"></a>Проверка включения Fluid Framework с помощью SharePoint PowerShell

1. [Подключение SharePoint PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps#to-connect-with-a-user-name-and-password). 

2. Проверьте, Fluid Framework включена ли Get-SPOTenant без аргументов.

3. Убедитесь, что значение IsFluidEnabled **истинно.**

## <a name="enabling-the-fluid-framework-through-the-sharepoint-online-powershell-cmdlet"></a>Включение Fluid Framework с помощью SharePoint PowerShell 

1. [Подключение SharePoint PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps#to-connect-with-a-user-name-and-password). 

2. Включить плавную текучесть с Set-SPOTenant -IsFluidEnabled $true 
   
   Это изменение будет применяться в течение короткого времени. 

Эта функция будет доступна на компьютере Teams Windows, Mac, iOS, Android. Если эта возможность включена, пользователи увидят новый параметр для вставки компонентов в прямом эфире в окну сообщений для этих клиентов.

## <a name="disabling-fluid-framework-through-sharepoint-online-powershell-cmdlet"></a>Отключение Fluid Framework с помощью SharePoint PowerShell Online

1. [Подключение SharePoint PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).

2. Отключать плавную Set-SPOTenant с помощью Set-SPOTenant -IsFluidEnabled $false. 

   Это изменение будет применяться в течение короткого времени. 

Если вам нужно снова включить эту возможность, вы можете использовать SharePoint PowerShell Online.

```powershell
C:\\WINDOWS\\system32&gt; Connect-SPOService
cmdlet Connect-SPOService at command pipeline position 1

Supply values for the following parameters:
Url: <https://a830edad9050849822e21011208-admin.sharepoint.com/>
PS C:\\WINDOWS\\system32&gt; set-SPOTenant -isFluidEnabled $false
PS C:\\WINDOWS\\system32&gt;
```

## <a name="known-limitations"></a>Известные ограничения

- Создание таблицы или списка задач в качестве первого компонента после Teams приложения может занять дополнительное время.

- Другие участники чата получат уведомление по электронной почте при упоминаний с символом @. (Уведомления по at-mentions в веб-Teams активности будут доступны в ближайшее время.)

- При поиске в Teams будет возвращена ссылка на компонент в office.com, а не на само сообщение чата.

- Живые компоненты отключены в федераированных чатах и включены для обычных чатов с гостевой учетной записью с помощью Azure B2B.

- Хотя вы можете поделиться компонентом в Teams каналах и других Microsoft 365, получатели получают ссылку в большинстве мест в настоящее время. В будущем планируется редактирование в режиме в том же режиме.

## <a name="storage-of-fluid-files"></a>служба хранилища `.fluid` файлов

**Как `.fluid` хранятся?**

Компоненты, созданные Teams, создаются на `.fluid` OneDrive для бизнеса. Если файл находится в OneDrive для бизнеса пользователи могут создавать компоненты (файлы) и управлять ими, а также управлять ими так же легко, как `.fluid` Office документ.

Пользователи могут искать содержимое в файлах `.fluid` с Office.com и OneDrive для бизнеса.
`.fluid` файлы работают с функциями управления данными, например с помощью функций eDiscovery, аудита, отчетности и удержания по юридическим вопросам.

`.fluid`теперь файлы будут отображаться на Office.com и OneDrive для бизнеса, например в области Последние и Рекомендуемые.
`.fluid`файлы можно восстановить в предыдущих версиях из OneDrive для бизнеса.

У участников чата должна быть OneDrive учетная запись, чтобы создавать компоненты в прямом эфире. Если у вас OneDrive учетная запись, участники чата могут по-прежнему иметь возможность совместно работать над компонентом, созданным другими пользователями, у которых есть действительная учетная запись OneDrive, но не может создать собственную.

[При](https://support.microsoft.com/en-us/office/move-files-and-folders-between-onedrive-and-sharepoint-5916f90d-f58a-4bf9-b135-10853f516d0b) перемещении файла OneDrive на веб-сайт SharePoint не удается загрузить его в чат Teams `.fluid` чате.

**Что произойдет, если владелец файла покидает компанию?**

[OneDrive политики хранения](/microsoft-365/compliance/retention-policies-sharepoint?view=o365-worldwide#when-a-user-leaves-the-organization) применяются к файлам точно так же, как к `.fluid` другому контенту, созданному пользователем.

**Как можно `.fluid` делиться файлами?**

Живые компоненты можно вставлять в Teams чате или копировать из одного чата в другой. (Компоненты live пока не поддерживаются в каналах.) Они по умолчанию имеют существующие разрешения клиента, но пользователи могут изменять разрешения перед отправкой, чтобы обеспечить доступ для всех пользователей.

При открытии компонентов из Teams чата в Office.com в верхней части окна доступны функции общего доступа, аналогичные возможностям общего доступа для других Office документов.

**Что делать, `.fluid` если файл поврежден или поврежден?**

История версий позволяет просмотреть и скопировать файл из предыдущих версий.

**Какие приложения могут открывать и редактировать `.fluid` файлы?**

`.fluid`файлы можно открывать только как ссылки в браузере, например Office.com, и как компоненты в Teams чате. Если они скачались, их невозможно снова открыть, не загрузив их обратно в OneDrive для бизнеса или SharePoint Online.
