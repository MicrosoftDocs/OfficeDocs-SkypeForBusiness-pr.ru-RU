---
title: Интеграция стороннего приложения для совместной работы с Lync
description: Интеграция стороннего приложения для совместной работы с Lync.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Integrating a third-party collaboration application with Lync
ms:assetid: 00b9312c-b0c8-4f79-8b76-05b2d820e197
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398068(v=OCS.15)
ms:contentKeyID: 48183224
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7adbe1abab83a569f581af034fc46abfef4cf819
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552655"
---
# <a name="integrating-a-third-party-collaboration-application-with-lync-server-2013"></a><span data-ttu-id="67862-103">Интеграция стороннего приложения для совместной работы с Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="67862-103">Integrating a third-party collaboration application with Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="67862-104">_**Последнее изменение темы:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="67862-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="67862-105">Вы можете интегрировать Lync 2013 со сторонним приложением для совместной работы в Интернете, добавив сведения о приложении в реестр.</span><span class="sxs-lookup"><span data-stu-id="67862-105">You can integrate Lync 2013 with any third-party online collaboration application by adding information about the application to the registry.</span></span> <span data-ttu-id="67862-106">Вы можете использовать Lync 2013 для запуска сеансов конференц-связи с данными, размещенных на внутреннем сервере, в Интернет-службе или в обоих случаях.</span><span class="sxs-lookup"><span data-stu-id="67862-106">You can use Lync 2013 to start data conferencing sessions hosted on an in-house server, an Internet-based service, or both.</span></span> <span data-ttu-id="67862-107">Сеанс совместной работы или конференц-связи можно запустить из списка контактов или из существующего сеанса обмена мгновенными сообщениями, голоса или видео.</span><span class="sxs-lookup"><span data-stu-id="67862-107">The collaboration or data conferencing session can be started from the Contacts list or from an existing instant messaging, voice, or video session.</span></span> <span data-ttu-id="67862-108">Lync 2013 действует только как транспортное средство для запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="67862-108">Lync 2013 acts only as the vehicle for starting the application.</span></span> <span data-ttu-id="67862-109">Все существующие беседы Lync 2013 будут активны после начала сеанса совместной работы в Интернете.</span><span class="sxs-lookup"><span data-stu-id="67862-109">Any existing Lync 2013 conversations remain active after the online collaboration session has begun.</span></span>

<span data-ttu-id="67862-110">В следующих разделах описано, как интегрировать Lync 2013 с приложениями совместной работы на основе Интернета и сервера.</span><span class="sxs-lookup"><span data-stu-id="67862-110">The following sections describe how to integrate Lync 2013 with Internet-based and server-based collaboration applications.</span></span>

<div>

## <a name="integrating-an-internet-based-collaboration-application-with-lync-2013"></a><span data-ttu-id="67862-111">Интеграция приложения для совместной работы Internet-Based с Lync 2013</span><span class="sxs-lookup"><span data-stu-id="67862-111">Integrating an Internet-Based Collaboration Application with Lync 2013</span></span>

<span data-ttu-id="67862-112">Как правило, для интеграции приложения для совместной работы с другими участниками используются следующие действия:</span><span class="sxs-lookup"><span data-stu-id="67862-112">Generally, the steps involved in integrating a third-party collaboration application are as follows:</span></span>

1.  <span data-ttu-id="67862-113">Сведения о приложении добавляются в реестр.</span><span class="sxs-lookup"><span data-stu-id="67862-113">Information about the application is added to the registry.</span></span>

2.  <span data-ttu-id="67862-114">Организатор входит в Lync 2013 и выбирает контакты для общего доступа к данным и совместной работы.</span><span class="sxs-lookup"><span data-stu-id="67862-114">The organizer signs in to Lync 2013 and selects contacts for data sharing and collaboration.</span></span> <span data-ttu-id="67862-115">Возможно также, что Организатор уже находится в беседе и решили добавить Конференц-связь с данными.</span><span class="sxs-lookup"><span data-stu-id="67862-115">Or, the organizer may already be in a conversation and decide to add data conferencing.</span></span>

3.  <span data-ttu-id="67862-116">Lync 2013 считывает реестр, запускает приложение для совместной работы, а затем отправляет настраиваемое сообщение SIP (Аппинвите) выбранным участникам.</span><span class="sxs-lookup"><span data-stu-id="67862-116">Lync 2013 reads the registry, starts the collaboration application, and then sends a custom SIP message—an appINVITE—to the selected participants.</span></span>

4.  <span data-ttu-id="67862-117">Участники принимают приглашение, и приложение совместной работы запускается на каждом компьютере пользователя.</span><span class="sxs-lookup"><span data-stu-id="67862-117">Participants accept the invitation, and the collaboration application is started on each person’s computer.</span></span> <span data-ttu-id="67862-118">Lync 2013 использует реестр для определения используемого приложения совместной работы, а затем запускает его, используя параметры, включенные в сообщение Аппинвите.</span><span class="sxs-lookup"><span data-stu-id="67862-118">Lync 2013 uses the registry to determine which collaboration application to use, and then starts that application by using the parameters included in the appINVITE message.</span></span>

<span data-ttu-id="67862-119">В следующей таблице описаны записи реестра, необходимые для интеграции приложения для совместной работы в Интернете с Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="67862-119">The following table describes the registry entries required to integrate an Internet-based collaboration application with Lync 2013.</span></span> <span data-ttu-id="67862-120">Эти записи размещаются в реестре в следующем расположении:</span><span class="sxs-lookup"><span data-stu-id="67862-120">These entries are placed in the registry in the following location:</span></span>

  - <span data-ttu-id="67862-121">\_ \_ Программное обеспечение для ЛОКАЛЬНОГО компьютера hKey \\ \\ \\ \\ \\ \\ \\ \\ Параметры приложений Microsoft Office 15,0 Lync сессионманажер</span><span class="sxs-lookup"><span data-stu-id="67862-121">HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters</span></span>

### <a name="registry-entries-for-an-internet-based-collaboration-application"></a><span data-ttu-id="67862-122">Записи реестра для приложения совместной работы на основе Интернета</span><span class="sxs-lookup"><span data-stu-id="67862-122">Registry Entries for an Internet-based Collaboration Application</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="67862-123">Имя</span><span class="sxs-lookup"><span data-stu-id="67862-123">Name</span></span></th>
<th><span data-ttu-id="67862-124">Тип</span><span class="sxs-lookup"><span data-stu-id="67862-124">Type</span></span></th>
<th><span data-ttu-id="67862-125">Данные</span><span class="sxs-lookup"><span data-stu-id="67862-125">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="67862-126">Имя</span><span class="sxs-lookup"><span data-stu-id="67862-126">Name</span></span></p></td>
<td><p><span data-ttu-id="67862-127">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="67862-127">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="67862-128">Имя приложения для меню Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="67862-128">The application name for Lync 2013 menus.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67862-129">смалликон</span><span class="sxs-lookup"><span data-stu-id="67862-129">SmallIcon</span></span></p></td>
<td><p><span data-ttu-id="67862-130">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="67862-130">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="67862-131">Путь к значку 16 x 16 пикселей, BMP или PNG.</span><span class="sxs-lookup"><span data-stu-id="67862-131">Path to 16-pixel x 16-pixel icon, BMP or PNG.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67862-132">Path</span><span class="sxs-lookup"><span data-stu-id="67862-132">Path</span></span></p></td>
<td><p><span data-ttu-id="67862-133">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="67862-133">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="67862-134">Путь участника для запуска приложения для совместной работы в Интернете.</span><span class="sxs-lookup"><span data-stu-id="67862-134">Participant path for starting the online collaboration application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67862-135">оригинаторпас</span><span class="sxs-lookup"><span data-stu-id="67862-135">OriginatorPath</span></span></p></td>
<td><p><span data-ttu-id="67862-136">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="67862-136">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="67862-137">Путь организатора для запуска приложения для совместной работы в Интернете.</span><span class="sxs-lookup"><span data-stu-id="67862-137">Organizer path for starting the online collaboration application.</span></span> <span data-ttu-id="67862-138">Этот путь может содержать один или несколько настраиваемых параметров, определенных в подразделе Parameters.</span><span class="sxs-lookup"><span data-stu-id="67862-138">This path can contain one or more custom parameters as defined in the Parameters subkey.</span></span> <span data-ttu-id="67862-139">Пример: <code>https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&amp;role=present&amp;pw=%param3%</code></span><span class="sxs-lookup"><span data-stu-id="67862-139">For example, <code>https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&amp;role=present&amp;pw=%param3%</code></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67862-140">сессионтипе</span><span class="sxs-lookup"><span data-stu-id="67862-140">SessionType</span></span></p></td>
<td><p><span data-ttu-id="67862-141">DWORD</span><span class="sxs-lookup"><span data-stu-id="67862-141">DWORD</span></span></p></td>
<td><p><span data-ttu-id="67862-142">0 = локальный сеанс.</span><span class="sxs-lookup"><span data-stu-id="67862-142">0 = Local session.</span></span> <span data-ttu-id="67862-143">Приложение запускается на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="67862-143">The application is started on the local computer.</span></span></p>
<p><span data-ttu-id="67862-144">1 = двусторонний сеанс (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="67862-144">1 = Two-party session (default).</span></span> <span data-ttu-id="67862-145">Lync 2013 запускает приложение локально, а затем отправляет системное уведомление другому пользователю.</span><span class="sxs-lookup"><span data-stu-id="67862-145">Lync 2013 starts the application locally, and then sends a system notification to the other user.</span></span> <span data-ttu-id="67862-146">Другой пользователь щелкает уведомление и запускает указанное приложение на своем компьютере.</span><span class="sxs-lookup"><span data-stu-id="67862-146">The other user clicks the notification and starts the specified application on their computer.</span></span></p>
<p><span data-ttu-id="67862-147">2 = многокомпонентный сеанс.</span><span class="sxs-lookup"><span data-stu-id="67862-147">2 = Multiparty session.</span></span> <span data-ttu-id="67862-148">Lync 2013 запускает приложение локально, а затем отправляет системные уведомления другим пользователям, предложи им запустить указанное приложение на своем компьютере.</span><span class="sxs-lookup"><span data-stu-id="67862-148">Lync 2013 starts the application locally, and then sends system notifications to the other users, prompting them to start the specified application on their own computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67862-149">ексенсиблемену</span><span class="sxs-lookup"><span data-stu-id="67862-149">ExensibleMenu</span></span></p></td>
<td><p><span data-ttu-id="67862-150">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="67862-150">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="67862-151">Список меню, в котором будет отображаться эта команда, разделенных точкой с запятой.</span><span class="sxs-lookup"><span data-stu-id="67862-151">A list of the menus where this command will appear, separated by semi-colons.</span></span> <span data-ttu-id="67862-152">Возможные значения:</span><span class="sxs-lookup"><span data-stu-id="67862-152">Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="67862-153">маинвиндовактионс</span><span class="sxs-lookup"><span data-stu-id="67862-153">MainWindowActions</span></span></p></li>
<li><p><span data-ttu-id="67862-154">маинвиндовригхткликк</span><span class="sxs-lookup"><span data-stu-id="67862-154">MainWindowRightClick</span></span></p></li>
<li><p><span data-ttu-id="67862-155">конверсатионвиндовактионс</span><span class="sxs-lookup"><span data-stu-id="67862-155">ConversationWindowActions</span></span></p></li>
<li><p><span data-ttu-id="67862-156">конверсатионвиндовбуттон</span><span class="sxs-lookup"><span data-stu-id="67862-156">ConversationWindowButton</span></span></p></li>
<li><p><span data-ttu-id="67862-157">конверсатионвиндовригхткликк</span><span class="sxs-lookup"><span data-stu-id="67862-157">ConversationWindowRightClick</span></span></p></li>
</ul>
<p><span data-ttu-id="67862-158">Если Екстенсиблемену не определен, используются значения по умолчанию Маинвиндовригхткликк и Конверсатионвиндовактионс.</span><span class="sxs-lookup"><span data-stu-id="67862-158">If ExtensibleMenu is not defined, the default values of MainWindowRightClick and ConversationWindowActions are used.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="67862-159">В следующей таблице описаны записи реестра для параметров.</span><span class="sxs-lookup"><span data-stu-id="67862-159">The following table describes the registry entries for parameters.</span></span> <span data-ttu-id="67862-160">Эти записи находятся на странице HKEY \_ текущий \_ пользователь \\ , \\ Microsoft \\ Office \\ 15,0 \\ Lync \\ сессионманажер \\ \\ Параметры приложений.</span><span class="sxs-lookup"><span data-stu-id="67862-160">These entries are place at HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters.</span></span>

### <a name="registry-entries-for-an-internet-based-collaboration-application"></a><span data-ttu-id="67862-161">Записи реестра для приложения совместной работы на основе Интернета</span><span class="sxs-lookup"><span data-stu-id="67862-161">Registry Entries for an Internet-based Collaboration Application</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="67862-162">Имя</span><span class="sxs-lookup"><span data-stu-id="67862-162">Name</span></span></th>
<th><span data-ttu-id="67862-163">Тип</span><span class="sxs-lookup"><span data-stu-id="67862-163">Type</span></span></th>
<th><span data-ttu-id="67862-164">Данные</span><span class="sxs-lookup"><span data-stu-id="67862-164">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="67862-165">Параметр1</span><span class="sxs-lookup"><span data-stu-id="67862-165">Param1</span></span></p></td>
<td><p><span data-ttu-id="67862-166">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="67862-166">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="67862-167">Используется в маркерном формате ( <code>%Parm1%</code> ) для добавления значений, относящихся к пользователю, в раздел реестра оригинаторпас.</span><span class="sxs-lookup"><span data-stu-id="67862-167">Used in tokenized format (<code>%Parm1%</code>) to add user-specific values to the OriginatorPath registry key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67862-168">Param2</span><span class="sxs-lookup"><span data-stu-id="67862-168">Param2</span></span></p></td>
<td><p><span data-ttu-id="67862-169">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="67862-169">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="67862-170">Обратитесь к разделу Param1.</span><span class="sxs-lookup"><span data-stu-id="67862-170">See Param1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67862-171">Param3</span><span class="sxs-lookup"><span data-stu-id="67862-171">Param3</span></span></p></td>
<td><p><span data-ttu-id="67862-172">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="67862-172">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="67862-173">Обратитесь к разделу Param1.</span><span class="sxs-lookup"><span data-stu-id="67862-173">See Param1.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="67862-174">В приведенном ниже примере параметры реестра интегрируют клиент ADatum для совместной работы с Lync 2013:</span><span class="sxs-lookup"><span data-stu-id="67862-174">The following example registry settings integrate ADatum Collaboration Client with Lync 2013:</span></span>

    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps\{C3F6E17A-855F-44a0-B90D-C0B92D38E5F1}]
    "Path"="https://meetingservice.adatum.com/cc/%param1%/meet/%param2%"
    "OriginatorPath"="https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&role=present&pw=%param3%"
    "SessionType"=dword:00000002
    "ApplicationType"=dword:00000001
    "LiveServerIntegration"=dword:00000000
    "Name"="ADatum Online Collaboration Service"
    "Extensiblemenu"="MainWindowActions;MainWindowRightClick;ConversationWindowActions;ConversationWindowRightClick"
    
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager]
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager\Apps]
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager\Apps\Parameters]
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager\Apps\Parameters\{C3F6E17A-855F-44a0-B90D-C0B92D38E5F1}]
    "Param1"="meetserv"
    "Param2"="admin"
    "Param3"="abcdefg123"

</div>

<div>

## <a name="integrating-a-server-based-collaboration-application-with-lync-2013"></a><span data-ttu-id="67862-175">Интеграция приложения для совместной работы Server-Based с Lync 2013</span><span class="sxs-lookup"><span data-stu-id="67862-175">Integrating a Server-Based Collaboration Application with Lync 2013</span></span>

<span data-ttu-id="67862-176">Параметры добавления команд для запуска приложения совместной работы на основе сервера в Lync 2013 аналогичны тем, которые описаны в предыдущем разделе, интеграция приложения для совместной работы Internet-Based с Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="67862-176">The settings to add commands for starting a server-based collaboration application from within Lync 2013 are similar to those described in the previous section, Integrating an Internet-Based Collaboration Application with Lync 2013.</span></span> <span data-ttu-id="67862-177">Однако Оригинаторпас не является обязательным, и некоторые значения изменяются.</span><span class="sxs-lookup"><span data-stu-id="67862-177">However, the OriginatorPath is not required, and some values are changed.</span></span> <span data-ttu-id="67862-178">Записи реестра размещаются в следующем расположении:</span><span class="sxs-lookup"><span data-stu-id="67862-178">Registry entries are placed in the following location:</span></span>

  - <span data-ttu-id="67862-179">\_ \_ Программное обеспечение для ЛОКАЛЬНОГО компьютера hKey \\ \\ \\ \\ \\ \\ \\ \\ Параметры приложений Microsoft Office 15,0 Lync сессионманажер</span><span class="sxs-lookup"><span data-stu-id="67862-179">HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters</span></span>

### <a name="registry-entries-for-a-server-based-collaboration-application"></a><span data-ttu-id="67862-180">Записи реестра для приложения совместной работы на основе сервера</span><span class="sxs-lookup"><span data-stu-id="67862-180">Registry Entries for a Server-based Collaboration Application</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="67862-181">Имя</span><span class="sxs-lookup"><span data-stu-id="67862-181">Name</span></span></th>
<th><span data-ttu-id="67862-182">Тип</span><span class="sxs-lookup"><span data-stu-id="67862-182">Type</span></span></th>
<th><span data-ttu-id="67862-183">Данные</span><span class="sxs-lookup"><span data-stu-id="67862-183">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="67862-184">Имя</span><span class="sxs-lookup"><span data-stu-id="67862-184">Name</span></span></p></td>
<td><p><span data-ttu-id="67862-185">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="67862-185">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="67862-186">Имя приложения в том виде, в котором оно отображается в меню.</span><span class="sxs-lookup"><span data-stu-id="67862-186">Name of the application as it appears on the menu.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67862-187">ApplicationType</span><span class="sxs-lookup"><span data-stu-id="67862-187">ApplicationType</span></span></p></td>
<td><p><span data-ttu-id="67862-188">DWORD</span><span class="sxs-lookup"><span data-stu-id="67862-188">DWORD</span></span></p></td>
<td><p><span data-ttu-id="67862-189">Значение = 1.</span><span class="sxs-lookup"><span data-stu-id="67862-189">Value = 1.</span></span> <span data-ttu-id="67862-190">Задает тип приложения "протокол".</span><span class="sxs-lookup"><span data-stu-id="67862-190">Sets the application type to protocol.</span></span> <span data-ttu-id="67862-191">Другие возможные значения в этом случае не применяются.</span><span class="sxs-lookup"><span data-stu-id="67862-191">The other possible values do not apply in this case.</span></span> <span data-ttu-id="67862-192">Если этот параметр отсутствует, Аппликатионтипе имеет значение 0 (исполняемый файл).</span><span class="sxs-lookup"><span data-stu-id="67862-192">If not present, ApplicationType is set to 0 (executable).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67862-193">Path</span><span class="sxs-lookup"><span data-stu-id="67862-193">Path</span></span></p></td>
<td><p><span data-ttu-id="67862-194">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="67862-194">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="67862-195">Протокол, используемый для запуска приложения совместной работы.</span><span class="sxs-lookup"><span data-stu-id="67862-195">Protocol used to start the collaboration application.</span></span> <span data-ttu-id="67862-196">Для Live Meeting 2007 для параметра path задается значение <code>meet:%conf-uri%</code> .</span><span class="sxs-lookup"><span data-stu-id="67862-196">For Live Meeting 2007, the value of Path is set to <code>meet:%conf-uri%</code>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67862-197">сессионтипе</span><span class="sxs-lookup"><span data-stu-id="67862-197">SessionType</span></span></p></td>
<td><p><span data-ttu-id="67862-198">DWORD</span><span class="sxs-lookup"><span data-stu-id="67862-198">DWORD</span></span></p></td>
<td><p><span data-ttu-id="67862-199">0 = локальный сеанс.</span><span class="sxs-lookup"><span data-stu-id="67862-199">0 = Local session.</span></span> <span data-ttu-id="67862-200">Приложение запускается на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="67862-200">The application is started on the local computer.</span></span></p>
<p><span data-ttu-id="67862-201">1 = двусторонний сеанс (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="67862-201">1 = Two-party session (default).</span></span> <span data-ttu-id="67862-202">Lync 2013 запускает приложение локально, а затем отправляет системное уведомление другому пользователю.</span><span class="sxs-lookup"><span data-stu-id="67862-202">Lync 2013 starts the application locally, and then sends a system notification to the other user.</span></span> <span data-ttu-id="67862-203">Другой пользователь щелкает уведомление и запускает указанное приложение на своем компьютере.</span><span class="sxs-lookup"><span data-stu-id="67862-203">The other user clicks the notification and starts the specified application on their computer.</span></span></p>
<p><span data-ttu-id="67862-204">2 = многокомпонентный сеанс.</span><span class="sxs-lookup"><span data-stu-id="67862-204">2 = Multiparty session.</span></span> <span data-ttu-id="67862-205">Lync 2013 запускает приложение локально, а затем отправляет системные уведомления другим пользователям, предложи им запустить указанное приложение на своем компьютере.</span><span class="sxs-lookup"><span data-stu-id="67862-205">Lync 2013 starts the application locally, and then sends system notifications to the other users, prompting them to start the specified application on their computer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67862-206">мкутипе</span><span class="sxs-lookup"><span data-stu-id="67862-206">MCUType</span></span></p></td>
<td><p><span data-ttu-id="67862-207">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="67862-207">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="67862-208">DATA = тип сервера.</span><span class="sxs-lookup"><span data-stu-id="67862-208">DATA = The type of server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67862-209">екстенсиблемену</span><span class="sxs-lookup"><span data-stu-id="67862-209">ExtensibleMenu</span></span></p></td>
<td><p><span data-ttu-id="67862-210">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="67862-210">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="67862-211">Список меню, в котором будет отображаться эта команда, разделенных точкой с запятой.</span><span class="sxs-lookup"><span data-stu-id="67862-211">A list of the menus where this command will appear, separated by semicolons.</span></span> <span data-ttu-id="67862-212">Возможные значения:</span><span class="sxs-lookup"><span data-stu-id="67862-212">Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="67862-213">маинвиндовактионс</span><span class="sxs-lookup"><span data-stu-id="67862-213">MainWindowActions</span></span></p></li>
<li><p><span data-ttu-id="67862-214">маинвиндовригхткликк</span><span class="sxs-lookup"><span data-stu-id="67862-214">MainWindowRightClick</span></span></p></li>
<li><p><span data-ttu-id="67862-215">конверсатионвиндовактионс</span><span class="sxs-lookup"><span data-stu-id="67862-215">ConversationWindowActions</span></span></p></li>
<li><p><span data-ttu-id="67862-216">конверсатионвиндовбуттон</span><span class="sxs-lookup"><span data-stu-id="67862-216">ConversationWindowButton</span></span></p></li>
<li><p><span data-ttu-id="67862-217">конверсатионвиндовригхткликк</span><span class="sxs-lookup"><span data-stu-id="67862-217">ConversationWindowRightClick</span></span></p></li>
</ul>
<p><span data-ttu-id="67862-218">Если Екстенсиблемену не определен, используются значения по умолчанию Маинвиндовригхткликк и Конверсатионвиндовактионс.</span><span class="sxs-lookup"><span data-stu-id="67862-218">If ExtensibleMenu is not defined, the default values of MainWindowRightClick and ConversationWindowActions are used.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="67862-219">В следующем примере показано, как добавить команды для запуска клиента совместной работы ADatum из Lync 2013:</span><span class="sxs-lookup"><span data-stu-id="67862-219">The following example adds commands to start ADatum Collaboration Client from within Lync 2013:</span></span>

    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps\{27877e66-615c-4582-ab88-0cb2ca05d951}]
    "Path"="meet:%conf-uri%"
    "SessionType"=dword:00000002
    "LiveServerIntegration"=dword:00000001
    "ApplicationType"=dword:00000001
    "Name"="ADatum Collaboration Client"
    "MCUType"="Data"
    "Extensiblemenu"="MainWindowActions;MainWindowRightClick;ConversationWindowActions;ConversationWindowRightClick"

</div>

</div>

<span> </span>

</div>

</div>

</div>

