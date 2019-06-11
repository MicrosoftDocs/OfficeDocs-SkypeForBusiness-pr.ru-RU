---
title: 'Lync Server 2013: Добавление команд в меню Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Adding commands to Lync menus
ms:assetid: a8443bc2-e234-4022-870a-00700f38b1ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412788(v=OCS.15)
ms:contentKeyID: 48185091
ms.date: 04/11/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1dfb79a985791e6994d8409339d12b12e1146ec5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841936"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="adding-commands-to-lync-menus-in-lync-server-2013"></a><span data-ttu-id="15d03-102">Добавление команд в меню Lync на сервере Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15d03-102">Adding commands to Lync menus in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="15d03-103">_**Тема последнего изменения:** 2016-04-11_</span><span class="sxs-lookup"><span data-stu-id="15d03-103">_**Topic Last Modified:** 2016-04-11_</span></span>

<span data-ttu-id="15d03-104">Вы можете добавить пользовательские команды в меню Lync 2013 и передать ей универсальный код ресурса (URI) текущего пользователя и выбранные контакты в приложение, с которого запускается пользовательская команда.</span><span class="sxs-lookup"><span data-stu-id="15d03-104">You can add custom commands to Lync 2013 menus and pass the SIP Uniform Resource Identifier (URI) of the current user and selected contacts to the application that the custom command starts.</span></span>

<span data-ttu-id="15d03-105">Пользовательские команды, которые вы добавляете, могут отображаться в одном или нескольких из следующих меню:</span><span class="sxs-lookup"><span data-stu-id="15d03-105">The custom commands that you add can appear on one or more of the following menus:</span></span>

  - <span data-ttu-id="15d03-106">Меню "Инструменты" в строке меню главного окна Lync</span><span class="sxs-lookup"><span data-stu-id="15d03-106">The Tools menu, on the menu bar in the Lync main window</span></span>

  - <span data-ttu-id="15d03-107">Контекстное меню контактов из списка контактов</span><span class="sxs-lookup"><span data-stu-id="15d03-107">The shortcut menu for contacts in the Contacts list</span></span>

  - <span data-ttu-id="15d03-108">Меню "Дополнительные параметры" в окне беседы</span><span class="sxs-lookup"><span data-stu-id="15d03-108">The More Options menu, in the Conversation window</span></span>

  - <span data-ttu-id="15d03-109">Контекстное меню пользователей, перечисленных в списке участников в окне беседы</span><span class="sxs-lookup"><span data-stu-id="15d03-109">The shortcut menu for people listed in the Conversation window participant list</span></span>

  - <span data-ttu-id="15d03-110">Меню "Параметры" в карточке контакта</span><span class="sxs-lookup"><span data-stu-id="15d03-110">The options menu in a contact card</span></span>

<span data-ttu-id="15d03-111">Вы можете определять пользовательские команды для двух типов приложений — приложений, которые выполняют одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="15d03-111">You can define custom commands for two types of applications—applications that do either of the following:</span></span>

  - <span data-ttu-id="15d03-112">Применимо только к текущему пользователю и запущены на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="15d03-112">Apply only to the current user and are started on the local computer.</span></span>

  - <span data-ttu-id="15d03-113">Включение дополнительных пользователей, например программы для совместной работы, которые должны быть запущены на компьютерах пользователей.</span><span class="sxs-lookup"><span data-stu-id="15d03-113">Involve additional users, such as an online collaboration program, and must be started on each user's computer.</span></span>

<span data-ttu-id="15d03-114">Настраиваемая команда может быть вызвана следующими способами:</span><span class="sxs-lookup"><span data-stu-id="15d03-114">The custom command can be invoked in the following ways:</span></span>

  - <span data-ttu-id="15d03-115">Выберите одного или нескольких пользователей, а затем выберите команду настраиваемая.</span><span class="sxs-lookup"><span data-stu-id="15d03-115">Select one or more users, and then choose the custom command.</span></span>

  - <span data-ttu-id="15d03-116">Начните двустороннюю или многосторонний разговор, а затем выберите команду "Настраиваемая".</span><span class="sxs-lookup"><span data-stu-id="15d03-116">Start a two-party or multiparty conversation, and then choose the custom command.</span></span>

<div>

## <a name="to-add-a-custom-command"></a><span data-ttu-id="15d03-117">Добавление настраиваемой команды</span><span class="sxs-lookup"><span data-stu-id="15d03-117">To add a custom command</span></span>

<span data-ttu-id="15d03-118">Добавьте команду в меню с помощью параметров реестра в приведенной ниже таблице.</span><span class="sxs-lookup"><span data-stu-id="15d03-118">Use the registry settings in the following table to add a command to the menus.</span></span> <span data-ttu-id="15d03-119">Эти записи размещаются в реестре в одном из следующих расположений:</span><span class="sxs-lookup"><span data-stu-id="15d03-119">These entries are placed in the registry at one of the following locations:</span></span>

  - <span data-ttu-id="15d03-120">Для 32-разрядной\_ОС\_:\\hKey\\, программное\\обеспечение\\для\\локального компьютера Microsoft\\Office\\15,0 Lync сессионманажер Apps</span><span class="sxs-lookup"><span data-stu-id="15d03-120">For 32bit OS: HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps</span></span>

  - <span data-ttu-id="15d03-121">Для 64-разрядных\_версий\_ОС\\:\\hKey\\для\\локального\\компьютера\\WOW6432Node\\Microsoft\\Office 15,0 Lync сессионманажер Apps</span><span class="sxs-lookup"><span data-stu-id="15d03-121">For 64bit OS: HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps</span></span>

### <a name="custom-command-registry-entries"></a><span data-ttu-id="15d03-122">Элементы реестра для настраиваемой команды</span><span class="sxs-lookup"><span data-stu-id="15d03-122">Custom Command Registry Entries</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="15d03-123">Имя</span><span class="sxs-lookup"><span data-stu-id="15d03-123">Name</span></span></th>
<th><span data-ttu-id="15d03-124">Тип</span><span class="sxs-lookup"><span data-stu-id="15d03-124">Type</span></span></th>
<th><span data-ttu-id="15d03-125">Значение</span><span class="sxs-lookup"><span data-stu-id="15d03-125">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="15d03-126">Имя</span><span class="sxs-lookup"><span data-stu-id="15d03-126">Name</span></span></p></td>
<td><p><span data-ttu-id="15d03-127">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="15d03-127">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="15d03-128">Имя приложения в том виде, в каком оно отображается в меню.</span><span class="sxs-lookup"><span data-stu-id="15d03-128">Name of the application as it appears on the menu.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15d03-129">Аппликатионтипе</span><span class="sxs-lookup"><span data-stu-id="15d03-129">ApplicationType</span></span></p></td>
<td><p><span data-ttu-id="15d03-130">@</span><span class="sxs-lookup"><span data-stu-id="15d03-130">DWORD</span></span></p></td>
<td><p><span data-ttu-id="15d03-131">0 = исполняемый файл (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="15d03-131">0 = Executable (default)</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="15d03-132">Требуется Аппликатионинсталлпас.</span><span class="sxs-lookup"><span data-stu-id="15d03-132">Requires ApplicationInstallPath.</span></span>


</div>
<p><span data-ttu-id="15d03-133">1 = протокол</span><span class="sxs-lookup"><span data-stu-id="15d03-133">1 = Protocol</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15d03-134">Аппликатионинсталлпас</span><span class="sxs-lookup"><span data-stu-id="15d03-134">ApplicationInstallPath</span></span></p></td>
<td><p><span data-ttu-id="15d03-135">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="15d03-135">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="15d03-136">Полный путь к исполняемому файлу.</span><span class="sxs-lookup"><span data-stu-id="15d03-136">Full path of the executable.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="15d03-137">Должен быть указан, если Аппликатионтипе имеет значение 0 (исполняемый объект).</span><span class="sxs-lookup"><span data-stu-id="15d03-137">Must be specified if ApplicationType is 0 (Executable).</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15d03-138">Путь</span><span class="sxs-lookup"><span data-stu-id="15d03-138">Path</span></span></p></td>
<td><p><span data-ttu-id="15d03-139">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="15d03-139">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="15d03-140">Полный путь, который необходимо запустить вместе с любыми параметрами, включая параметры по умолчанию <em>% ID пользователя</em> % и <em>% Contact-ID%</em>.</span><span class="sxs-lookup"><span data-stu-id="15d03-140">Full path to be started along with any parameters, including the default parameters <em>%user-id%</em> and <em>%contact-id%</em>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15d03-141">Сессионтипе</span><span class="sxs-lookup"><span data-stu-id="15d03-141">SessionType</span></span></p></td>
<td><p><span data-ttu-id="15d03-142">@</span><span class="sxs-lookup"><span data-stu-id="15d03-142">DWORD</span></span></p></td>
<td><p><span data-ttu-id="15d03-143">0 = локальный сеанс.</span><span class="sxs-lookup"><span data-stu-id="15d03-143">0 = Local session.</span></span> <span data-ttu-id="15d03-144">Приложение будет запущено на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="15d03-144">The application is started on the local computer.</span></span></p>
<p><span data-ttu-id="15d03-145">1 = два сеанса (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="15d03-145">1 = Two-party session (default).</span></span> <span data-ttu-id="15d03-146">Lync 2013 запускает приложение локально и отправляет уведомление на рабочем столе другому пользователю.</span><span class="sxs-lookup"><span data-stu-id="15d03-146">Lync 2013 starts the application locally and then sends a desktop notification to the other user.</span></span> <span data-ttu-id="15d03-147">Другой пользователь щелкает уведомление, чтобы запустить приложение на своем компьютере.</span><span class="sxs-lookup"><span data-stu-id="15d03-147">The other user clicks the notification to start the application on their computer.</span></span></p>
<p><span data-ttu-id="15d03-148">2 = многокомпонентный сеанс.</span><span class="sxs-lookup"><span data-stu-id="15d03-148">2 = Multiparty session.</span></span> <span data-ttu-id="15d03-149">Lync 2013 запускает приложение локально, а затем отправляет уведомления о рабочем столе другим пользователям.</span><span class="sxs-lookup"><span data-stu-id="15d03-149">Lync 2013 starts the application locally and then sends desktop notifications to the other users.</span></span> <span data-ttu-id="15d03-150">Другой пользователь щелкает уведомление, чтобы запустить указанное приложение на компьютере.</span><span class="sxs-lookup"><span data-stu-id="15d03-150">The other user clicks the notification to start the specified application on their computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15d03-151">Екстенсиблемену</span><span class="sxs-lookup"><span data-stu-id="15d03-151">ExtensibleMenu</span></span></p></td>
<td><p><span data-ttu-id="15d03-152">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="15d03-152">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="15d03-153">Список меню, в котором будет отображаться эта команда, разделенных точкой с запятой.</span><span class="sxs-lookup"><span data-stu-id="15d03-153">A list of the menus where this command will appear, separated by semicolons.</span></span> <span data-ttu-id="15d03-154">Возможные значения</span><span class="sxs-lookup"><span data-stu-id="15d03-154">Possible values are:</span></span></p>
<p><span data-ttu-id="15d03-155">Маинвиндовактионс</span><span class="sxs-lookup"><span data-stu-id="15d03-155">MainWindowActions</span></span></p>
<p><span data-ttu-id="15d03-156">Маинвиндовригхткликк</span><span class="sxs-lookup"><span data-stu-id="15d03-156">MainWindowRightClick</span></span></p>
<p><span data-ttu-id="15d03-157">Конверсатионвиндовактионс</span><span class="sxs-lookup"><span data-stu-id="15d03-157">ConversationWindowActions</span></span></p>
<p><span data-ttu-id="15d03-158">Конверсатионвиндовригхткликк</span><span class="sxs-lookup"><span data-stu-id="15d03-158">ConversationWindowRightClick</span></span></p>
<p><span data-ttu-id="15d03-159">Контакткардмену</span><span class="sxs-lookup"><span data-stu-id="15d03-159">ContactCardMenu</span></span></p>
<p><span data-ttu-id="15d03-160">Если Екстенсиблемену не определен, используются значения по умолчанию Маинвиндовригхткликк и Конверсатионвиндовактионс.</span><span class="sxs-lookup"><span data-stu-id="15d03-160">If ExtensibleMenu is not defined, the default values of MainWindowRightClick and ConversationWindowActions are used.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="15d03-161">Например, следующий редактор реестра (. REG-файл, в котором показано, как добавить элемент меню "продажи" для продаж Contoso в меню "действия" в окне беседы:</span><span class="sxs-lookup"><span data-stu-id="15d03-161">For example, the following Registry Editor (.REG) file shows the results of adding a Contoso Sales Contact Manager menu item to Actions menu in the Conversation window:</span></span>

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

## <a name="to-access-a-custom-command"></a><span data-ttu-id="15d03-162">Чтобы получить доступ к настраиваемой команде</span><span class="sxs-lookup"><span data-stu-id="15d03-162">To access a custom command</span></span>

<span data-ttu-id="15d03-163">Чтобы получить доступ к настраиваемой команде после ее добавления, выполните одно из указанных ниже действий в зависимости от указанных значений Екстенсиблемену.</span><span class="sxs-lookup"><span data-stu-id="15d03-163">To access a custom command after it is added, do one of the following, depending on the ExtensibleMenu values that you define:</span></span>

  - <span data-ttu-id="15d03-164">**Маинвиндовактионс**   в главном окне Lync нажмите кнопку **Сервис**и выберите пункт Настраиваемая команда.</span><span class="sxs-lookup"><span data-stu-id="15d03-164">**MainWindowActions**   In the Lync main window, click **Tools**, and then click your custom command.</span></span>

  - <span data-ttu-id="15d03-165">**Маинвиндовригхткликк**   . в главном окне Lync щелкните контакт правой кнопкой мыши и выберите команду "Настраиваемая".</span><span class="sxs-lookup"><span data-stu-id="15d03-165">**MainWindowRightClick**   In the Lync main window, right-click a contact, and then click your custom command.</span></span>

  - <span data-ttu-id="15d03-166">**Конверсатионвиндовактионс**   в окне беседы щелкните значок **Дополнительные параметры** и выберите нужную команду.</span><span class="sxs-lookup"><span data-stu-id="15d03-166">**ConversationWindowActions**   In the Conversation window, click the **More Options** icon, and then click your custom command.</span></span>

  - <span data-ttu-id="15d03-167">**Конверсатионвиндовригхткликк**   . в окне беседы щелкните правой кнопкой мыши имя контакта и выберите нужную команду.</span><span class="sxs-lookup"><span data-stu-id="15d03-167">**ConversationWindowRightClick**   In the Conversation window, right-click a contact name, and then click your custom command.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

