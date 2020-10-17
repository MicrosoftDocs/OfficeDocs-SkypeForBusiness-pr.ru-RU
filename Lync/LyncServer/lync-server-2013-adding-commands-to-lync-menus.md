---
title: 'Lync Server 2013: Добавление команд в меню Lync'
description: 'Lync Server 2013: Добавление команд в меню Lync.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Adding commands to Lync menus
ms:assetid: a8443bc2-e234-4022-870a-00700f38b1ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412788(v=OCS.15)
ms:contentKeyID: 48185091
ms.date: 04/11/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ed4d62d085eaf115d107244ae50a7cc69e0aacd5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558235"
---
# <a name="adding-commands-to-lync-menus-in-lync-server-2013"></a><span data-ttu-id="40c2d-103">Добавление команд в меню Lync в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="40c2d-103">Adding commands to Lync menus in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="40c2d-104">_**Последнее изменение темы:** 2016-04-11_</span><span class="sxs-lookup"><span data-stu-id="40c2d-104">_**Topic Last Modified:** 2016-04-11_</span></span>

<span data-ttu-id="40c2d-105">Вы можете добавлять пользовательские команды в меню Lync 2013 и передавать универсальный код ресурса (URI) SIP текущего пользователя и выбранные контакты в приложение, с которого начинается пользовательская команда.</span><span class="sxs-lookup"><span data-stu-id="40c2d-105">You can add custom commands to Lync 2013 menus and pass the SIP Uniform Resource Identifier (URI) of the current user and selected contacts to the application that the custom command starts.</span></span>

<span data-ttu-id="40c2d-106">Настраиваемые команды, которые вы добавляете, могут отображаться в одном или нескольких из следующих меню:</span><span class="sxs-lookup"><span data-stu-id="40c2d-106">The custom commands that you add can appear on one or more of the following menus:</span></span>

  - <span data-ttu-id="40c2d-107">Меню "Сервис" в строке меню в главном окне Lync</span><span class="sxs-lookup"><span data-stu-id="40c2d-107">The Tools menu, on the menu bar in the Lync main window</span></span>

  - <span data-ttu-id="40c2d-108">Контекстное меню контактов в списке контактов.</span><span class="sxs-lookup"><span data-stu-id="40c2d-108">The shortcut menu for contacts in the Contacts list</span></span>

  - <span data-ttu-id="40c2d-109">Меню дополнительных параметров в окне беседы</span><span class="sxs-lookup"><span data-stu-id="40c2d-109">The More Options menu, in the Conversation window</span></span>

  - <span data-ttu-id="40c2d-110">Контекстное меню для пользователей, перечисленных в списке участников окна беседы</span><span class="sxs-lookup"><span data-stu-id="40c2d-110">The shortcut menu for people listed in the Conversation window participant list</span></span>

  - <span data-ttu-id="40c2d-111">Меню параметров в карточке контакта</span><span class="sxs-lookup"><span data-stu-id="40c2d-111">The options menu in a contact card</span></span>

<span data-ttu-id="40c2d-112">Можно определить пользовательские команды для двух типов приложений — приложений, которые выполняют одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="40c2d-112">You can define custom commands for two types of applications—applications that do either of the following:</span></span>

  - <span data-ttu-id="40c2d-113">Применяется только к текущему пользователю и запускается на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="40c2d-113">Apply only to the current user and are started on the local computer.</span></span>

  - <span data-ttu-id="40c2d-114">Включение дополнительных пользователей, например программы для совместной работы, и их необходимо запускать на компьютере каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="40c2d-114">Involve additional users, such as an online collaboration program, and must be started on each user's computer.</span></span>

<span data-ttu-id="40c2d-115">Пользовательская команда может быть вызвана следующими способами:</span><span class="sxs-lookup"><span data-stu-id="40c2d-115">The custom command can be invoked in the following ways:</span></span>

  - <span data-ttu-id="40c2d-116">Выберите одного или нескольких пользователей, а затем выберите команду Пользовательская.</span><span class="sxs-lookup"><span data-stu-id="40c2d-116">Select one or more users, and then choose the custom command.</span></span>

  - <span data-ttu-id="40c2d-117">Начните двустороннюю или многосторонний разговор, а затем выберите команду Пользовательская.</span><span class="sxs-lookup"><span data-stu-id="40c2d-117">Start a two-party or multiparty conversation, and then choose the custom command.</span></span>

<div>

## <a name="to-add-a-custom-command"></a><span data-ttu-id="40c2d-118">Добавление настраиваемой команды</span><span class="sxs-lookup"><span data-stu-id="40c2d-118">To add a custom command</span></span>

<span data-ttu-id="40c2d-119">Используйте параметры реестра, указанные в приведенной ниже таблице, для добавления команды в меню.</span><span class="sxs-lookup"><span data-stu-id="40c2d-119">Use the registry settings in the following table to add a command to the menus.</span></span> <span data-ttu-id="40c2d-120">Эти записи размещаются в реестре в одном из следующих расположений:</span><span class="sxs-lookup"><span data-stu-id="40c2d-120">These entries are placed in the registry at one of the following locations:</span></span>

  - <span data-ttu-id="40c2d-121">Для 32 – 32 OS \_ : \_ программное обеспечение для ЛОКАЛЬНОГО компьютера hKey \\ \\ Microsoft \\ Office \\ 15,0 \\ Lync \\ сессионманажер \\ Apps</span><span class="sxs-lookup"><span data-stu-id="40c2d-121">For 32bit OS: HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps</span></span>

  - <span data-ttu-id="40c2d-122">Для 64 64 OS: \_ \_ \\ программное обеспечение для локального компьютера \\ WOW6432Node \\ Microsoft \\ Office \\ 15,0 \\ Lync \\ сессионманажер \\ Apps</span><span class="sxs-lookup"><span data-stu-id="40c2d-122">For 64bit OS: HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps</span></span>

### <a name="custom-command-registry-entries"></a><span data-ttu-id="40c2d-123">Записи реестра настраиваемых команд</span><span class="sxs-lookup"><span data-stu-id="40c2d-123">Custom Command Registry Entries</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="40c2d-124">Имя</span><span class="sxs-lookup"><span data-stu-id="40c2d-124">Name</span></span></th>
<th><span data-ttu-id="40c2d-125">Тип</span><span class="sxs-lookup"><span data-stu-id="40c2d-125">Type</span></span></th>
<th><span data-ttu-id="40c2d-126">Данные</span><span class="sxs-lookup"><span data-stu-id="40c2d-126">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="40c2d-127">Имя</span><span class="sxs-lookup"><span data-stu-id="40c2d-127">Name</span></span></p></td>
<td><p><span data-ttu-id="40c2d-128">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="40c2d-128">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="40c2d-129">Имя приложения в том виде, в котором оно отображается в меню.</span><span class="sxs-lookup"><span data-stu-id="40c2d-129">Name of the application as it appears on the menu.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40c2d-130">ApplicationType</span><span class="sxs-lookup"><span data-stu-id="40c2d-130">ApplicationType</span></span></p></td>
<td><p><span data-ttu-id="40c2d-131">DWORD</span><span class="sxs-lookup"><span data-stu-id="40c2d-131">DWORD</span></span></p></td>
<td><p><span data-ttu-id="40c2d-132">0 = исполняемый файл (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="40c2d-132">0 = Executable (default)</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="40c2d-133">Требуется Аппликатионинсталлпас.</span><span class="sxs-lookup"><span data-stu-id="40c2d-133">Requires ApplicationInstallPath.</span></span>


</div>
<p><span data-ttu-id="40c2d-134">1 = протокол</span><span class="sxs-lookup"><span data-stu-id="40c2d-134">1 = Protocol</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40c2d-135">аппликатионинсталлпас</span><span class="sxs-lookup"><span data-stu-id="40c2d-135">ApplicationInstallPath</span></span></p></td>
<td><p><span data-ttu-id="40c2d-136">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="40c2d-136">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="40c2d-137">Полный путь к исполняемому файлу.</span><span class="sxs-lookup"><span data-stu-id="40c2d-137">Full path of the executable.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="40c2d-138">Должен быть указан, если Аппликатионтипе имеет значение 0 (исполняемый файл).</span><span class="sxs-lookup"><span data-stu-id="40c2d-138">Must be specified if ApplicationType is 0 (Executable).</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40c2d-139">Path</span><span class="sxs-lookup"><span data-stu-id="40c2d-139">Path</span></span></p></td>
<td><p><span data-ttu-id="40c2d-140">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="40c2d-140">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="40c2d-141">Полный путь, который необходимо запустить вместе с параметрами, включая параметры по умолчанию <em>% User/ID%</em> и <em>% Contact – ID%</em>.</span><span class="sxs-lookup"><span data-stu-id="40c2d-141">Full path to be started along with any parameters, including the default parameters <em>%user-id%</em> and <em>%contact-id%</em>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40c2d-142">сессионтипе</span><span class="sxs-lookup"><span data-stu-id="40c2d-142">SessionType</span></span></p></td>
<td><p><span data-ttu-id="40c2d-143">DWORD</span><span class="sxs-lookup"><span data-stu-id="40c2d-143">DWORD</span></span></p></td>
<td><p><span data-ttu-id="40c2d-144">0 = локальный сеанс.</span><span class="sxs-lookup"><span data-stu-id="40c2d-144">0 = Local session.</span></span> <span data-ttu-id="40c2d-145">Приложение запускается на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="40c2d-145">The application is started on the local computer.</span></span></p>
<p><span data-ttu-id="40c2d-146">1 = двусторонний сеанс (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="40c2d-146">1 = Two-party session (default).</span></span> <span data-ttu-id="40c2d-147">Lync 2013 запускает приложение локально, а затем отправляет уведомление на Рабочий стол другому пользователю.</span><span class="sxs-lookup"><span data-stu-id="40c2d-147">Lync 2013 starts the application locally and then sends a desktop notification to the other user.</span></span> <span data-ttu-id="40c2d-148">Другой пользователь щелкает уведомление, чтобы запустить приложение на своем компьютере.</span><span class="sxs-lookup"><span data-stu-id="40c2d-148">The other user clicks the notification to start the application on their computer.</span></span></p>
<p><span data-ttu-id="40c2d-149">2 = многокомпонентный сеанс.</span><span class="sxs-lookup"><span data-stu-id="40c2d-149">2 = Multiparty session.</span></span> <span data-ttu-id="40c2d-150">Lync 2013 запускает приложение локально, а затем отправляет уведомления о рабочем столе другим пользователям.</span><span class="sxs-lookup"><span data-stu-id="40c2d-150">Lync 2013 starts the application locally and then sends desktop notifications to the other users.</span></span> <span data-ttu-id="40c2d-151">Другой пользователь щелкает уведомление, чтобы запустить указанное приложение на своем компьютере.</span><span class="sxs-lookup"><span data-stu-id="40c2d-151">The other user clicks the notification to start the specified application on their computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40c2d-152">екстенсиблемену</span><span class="sxs-lookup"><span data-stu-id="40c2d-152">ExtensibleMenu</span></span></p></td>
<td><p><span data-ttu-id="40c2d-153">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="40c2d-153">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="40c2d-154">Список меню, в котором будет отображаться эта команда, разделенных точкой с запятой.</span><span class="sxs-lookup"><span data-stu-id="40c2d-154">A list of the menus where this command will appear, separated by semicolons.</span></span> <span data-ttu-id="40c2d-155">Возможные значения:</span><span class="sxs-lookup"><span data-stu-id="40c2d-155">Possible values are:</span></span></p>
<p><span data-ttu-id="40c2d-156">маинвиндовактионс</span><span class="sxs-lookup"><span data-stu-id="40c2d-156">MainWindowActions</span></span></p>
<p><span data-ttu-id="40c2d-157">маинвиндовригхткликк</span><span class="sxs-lookup"><span data-stu-id="40c2d-157">MainWindowRightClick</span></span></p>
<p><span data-ttu-id="40c2d-158">конверсатионвиндовактионс</span><span class="sxs-lookup"><span data-stu-id="40c2d-158">ConversationWindowActions</span></span></p>
<p><span data-ttu-id="40c2d-159">конверсатионвиндовригхткликк</span><span class="sxs-lookup"><span data-stu-id="40c2d-159">ConversationWindowRightClick</span></span></p>
<p><span data-ttu-id="40c2d-160">контакткардмену</span><span class="sxs-lookup"><span data-stu-id="40c2d-160">ContactCardMenu</span></span></p>
<p><span data-ttu-id="40c2d-161">Если Екстенсиблемену не определен, используются значения по умолчанию Маинвиндовригхткликк и Конверсатионвиндовактионс.</span><span class="sxs-lookup"><span data-stu-id="40c2d-161">If ExtensibleMenu is not defined, the default values of MainWindowRightClick and ConversationWindowActions are used.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="40c2d-162">Например, в следующем редакторе реестра (. REG) в окне беседы отображаются результаты добавления пункта меню "Диспетчер контактов Contoso" в меню действий.</span><span class="sxs-lookup"><span data-stu-id="40c2d-162">For example, the following Registry Editor (.REG) file shows the results of adding a Contoso Sales Contact Manager menu item to Actions menu in the Conversation window:</span></span>

    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Office\15.0\Lync\SessionManager\Apps\{1F9F07C6-7E0B-462B-AAD7-98C6DBEA8F69}]
    "Name"="Contoso Sales Contact Manager"
    "HelpMessage"="The Contoso Sales Contact Manager is not installed. Contact the Help Desk for more information."
    "ApplicationType"=dword:00000000
    "ApplicationInstallPath"="C:\\cscm.exe"
    "Path"="C:\\cscm.exe %user-id% %contact-id%"
    "SessionType"=dword:00000001
    "ExtensibleMenu"="ConversationWindowActions;MainWindowRightClick"

</div>

<div>

## <a name="to-access-a-custom-command"></a><span data-ttu-id="40c2d-163">Доступ к настраиваемой команде</span><span class="sxs-lookup"><span data-stu-id="40c2d-163">To access a custom command</span></span>

<span data-ttu-id="40c2d-164">Чтобы получить доступ к настраиваемой команде после ее добавления, выполните одно из следующих действий в зависимости от определяемых значений Екстенсиблемену:</span><span class="sxs-lookup"><span data-stu-id="40c2d-164">To access a custom command after it is added, do one of the following, depending on the ExtensibleMenu values that you define:</span></span>

  - <span data-ttu-id="40c2d-165">**Маинвиндовактионс**     В главном окне Lync откройте меню **Сервис**и выберите команду Пользовательская.</span><span class="sxs-lookup"><span data-stu-id="40c2d-165">**MainWindowActions**   In the Lync main window, click **Tools**, and then click your custom command.</span></span>

  - <span data-ttu-id="40c2d-166">**Маинвиндовригхткликк**     В главном окне Lync щелкните контакт правой кнопкой мыши и выберите пользовательскую команду.</span><span class="sxs-lookup"><span data-stu-id="40c2d-166">**MainWindowRightClick**   In the Lync main window, right-click a contact, and then click your custom command.</span></span>

  - <span data-ttu-id="40c2d-167">**Конверсатионвиндовактионс**     В окне беседы щелкните значок **Дополнительные параметры** , а затем выберите пользовательскую команду.</span><span class="sxs-lookup"><span data-stu-id="40c2d-167">**ConversationWindowActions**   In the Conversation window, click the **More Options** icon, and then click your custom command.</span></span>

  - <span data-ttu-id="40c2d-168">**Конверсатионвиндовригхткликк**     В окне беседы щелкните правой кнопкой мыши имя контакта и выберите пользовательскую команду.</span><span class="sxs-lookup"><span data-stu-id="40c2d-168">**ConversationWindowRightClick**   In the Conversation window, right-click a contact name, and then click your custom command.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

