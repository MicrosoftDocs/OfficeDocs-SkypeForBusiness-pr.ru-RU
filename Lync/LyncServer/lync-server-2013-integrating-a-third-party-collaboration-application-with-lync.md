---
title: Интеграция стороннего приложения для совместной работы с Lync
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
ms.openlocfilehash: 6210591be9aaf281b76ea02f6f919ea3d1620db7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195832"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="integrating-a-third-party-collaboration-application-with-lync-server-2013"></a><span data-ttu-id="b5b4e-102">Интеграция стороннего приложения для совместной работы с Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5b4e-102">Integrating a third-party collaboration application with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b5b4e-103">_**Последнее изменение темы:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="b5b4e-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="b5b4e-104">Вы можете интегрировать Lync 2013 со сторонним приложением для совместной работы в Интернете, добавив сведения о приложении в реестр.</span><span class="sxs-lookup"><span data-stu-id="b5b4e-104">You can integrate Lync 2013 with any third-party online collaboration application by adding information about the application to the registry.</span></span> <span data-ttu-id="b5b4e-105">Вы можете использовать Lync 2013 для запуска сеансов конференц-связи с данными, размещенных на внутреннем сервере, в Интернет-службе или в обоих случаях.</span><span class="sxs-lookup"><span data-stu-id="b5b4e-105">You can use Lync 2013 to start data conferencing sessions hosted on an in-house server, an Internet-based service, or both.</span></span> <span data-ttu-id="b5b4e-106">Сеанс совместной работы или конференц-связи можно запустить из списка контактов или из существующего сеанса обмена мгновенными сообщениями, голоса или видео.</span><span class="sxs-lookup"><span data-stu-id="b5b4e-106">The collaboration or data conferencing session can be started from the Contacts list or from an existing instant messaging, voice, or video session.</span></span> <span data-ttu-id="b5b4e-107">Lync 2013 действует только как транспортное средство для запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="b5b4e-107">Lync 2013 acts only as the vehicle for starting the application.</span></span> <span data-ttu-id="b5b4e-108">Все существующие беседы Lync 2013 будут активны после начала сеанса совместной работы в Интернете.</span><span class="sxs-lookup"><span data-stu-id="b5b4e-108">Any existing Lync 2013 conversations remain active after the online collaboration session has begun.</span></span>

<span data-ttu-id="b5b4e-109">В следующих разделах описано, как интегрировать Lync 2013 с приложениями совместной работы на основе Интернета и сервера.</span><span class="sxs-lookup"><span data-stu-id="b5b4e-109">The following sections describe how to integrate Lync 2013 with Internet-based and server-based collaboration applications.</span></span>

<div>

## <a name="integrating-an-internet-based-collaboration-application-with-lync-2013"></a><span data-ttu-id="b5b4e-110">Интеграция приложения совместной работы на основе Интернета с Lync 2013</span><span class="sxs-lookup"><span data-stu-id="b5b4e-110">Integrating an Internet-Based Collaboration Application with Lync 2013</span></span>

<span data-ttu-id="b5b4e-111">Как правило, для интеграции приложения для совместной работы с другими участниками используются следующие действия:</span><span class="sxs-lookup"><span data-stu-id="b5b4e-111">Generally, the steps involved in integrating a third-party collaboration application are as follows:</span></span>

1.  <span data-ttu-id="b5b4e-112">Сведения о приложении добавляются в реестр.</span><span class="sxs-lookup"><span data-stu-id="b5b4e-112">Information about the application is added to the registry.</span></span>

2.  <span data-ttu-id="b5b4e-113">Организатор входит в Lync 2013 и выбирает контакты для общего доступа к данным и совместной работы.</span><span class="sxs-lookup"><span data-stu-id="b5b4e-113">The organizer signs in to Lync 2013 and selects contacts for data sharing and collaboration.</span></span> <span data-ttu-id="b5b4e-114">Возможно также, что Организатор уже находится в беседе и решили добавить Конференц-связь с данными.</span><span class="sxs-lookup"><span data-stu-id="b5b4e-114">Or, the organizer may already be in a conversation and decide to add data conferencing.</span></span>

3.  <span data-ttu-id="b5b4e-115">Lync 2013 считывает реестр, запускает приложение для совместной работы, а затем отправляет настраиваемое сообщение SIP (Аппинвите) выбранным участникам.</span><span class="sxs-lookup"><span data-stu-id="b5b4e-115">Lync 2013 reads the registry, starts the collaboration application, and then sends a custom SIP message—an appINVITE—to the selected participants.</span></span>

4.  <span data-ttu-id="b5b4e-116">Участники принимают приглашение, и приложение совместной работы запускается на каждом компьютере пользователя.</span><span class="sxs-lookup"><span data-stu-id="b5b4e-116">Participants accept the invitation, and the collaboration application is started on each person’s computer.</span></span> <span data-ttu-id="b5b4e-117">Lync 2013 использует реестр для определения используемого приложения совместной работы, а затем запускает его, используя параметры, включенные в сообщение Аппинвите.</span><span class="sxs-lookup"><span data-stu-id="b5b4e-117">Lync 2013 uses the registry to determine which collaboration application to use, and then starts that application by using the parameters included in the appINVITE message.</span></span>

<span data-ttu-id="b5b4e-118">В следующей таблице описаны записи реестра, необходимые для интеграции приложения для совместной работы в Интернете с Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="b5b4e-118">The following table describes the registry entries required to integrate an Internet-based collaboration application with Lync 2013.</span></span> <span data-ttu-id="b5b4e-119">Эти записи размещаются в реестре в следующем расположении:</span><span class="sxs-lookup"><span data-stu-id="b5b4e-119">These entries are placed in the registry in the following location:</span></span>

  - <span data-ttu-id="b5b4e-120">Программное\_обеспечение\\\\для локального\\компьютера\\hKey\\\_параметры\\приложений\\\\Microsoft Office 15,0 Lync сессионманажер</span><span class="sxs-lookup"><span data-stu-id="b5b4e-120">HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters</span></span>

### <a name="registry-entries-for-an-internet-based-collaboration-application"></a><span data-ttu-id="b5b4e-121">Записи реестра для приложения совместной работы на основе Интернета</span><span class="sxs-lookup"><span data-stu-id="b5b4e-121">Registry Entries for an Internet-based Collaboration Application</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b5b4e-122">Имя</span><span class="sxs-lookup"><span data-stu-id="b5b4e-122">Name</span></span></th>
<th><span data-ttu-id="b5b4e-123">Тип</span><span class="sxs-lookup"><span data-stu-id="b5b4e-123">Type</span></span></th>
<th><span data-ttu-id="b5b4e-124">Данные</span><span class="sxs-lookup"><span data-stu-id="b5b4e-124">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b5b4e-125">Имя</span><span class="sxs-lookup"><span data-stu-id="b5b4e-125">Name</span></span></p></td>
<td><p><span data-ttu-id="b5b4e-126">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="b5b4e-126">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="b5b4e-127">Имя приложения для меню Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="b5b4e-127">The application name for Lync 2013 menus.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5b4e-128">смалликон</span><span class="sxs-lookup"><span data-stu-id="b5b4e-128">SmallIcon</span></span></p></td>
<td><p><span data-ttu-id="b5b4e-129">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="b5b4e-129">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="b5b4e-130">Путь к значку 16 x 16 пикселей, BMP или PNG.</span><span class="sxs-lookup"><span data-stu-id="b5b4e-130">Path to 16-pixel x 16-pixel icon, BMP or PNG.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5b4e-131">Path</span><span class="sxs-lookup"><span data-stu-id="b5b4e-131">Path</span></span></p></td>
<td><p><span data-ttu-id="b5b4e-132">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="b5b4e-132">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="b5b4e-133">Путь участника для запуска приложения для совместной работы в Интернете.</span><span class="sxs-lookup"><span data-stu-id="b5b4e-133">Participant path for starting the online collaboration application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5b4e-134">оригинаторпас</span><span class="sxs-lookup"><span data-stu-id="b5b4e-134">OriginatorPath</span></span></p></td>
<td><p><span data-ttu-id="b5b4e-135">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="b5b4e-135">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="b5b4e-136">Путь организатора для запуска приложения для совместной работы в Интернете.</span><span class="sxs-lookup"><span data-stu-id="b5b4e-136">Organizer path for starting the online collaboration application.</span></span> <span data-ttu-id="b5b4e-137">Этот путь может содержать один или несколько настраиваемых параметров, определенных в подразделе Parameters.</span><span class="sxs-lookup"><span data-stu-id="b5b4e-137">This path can contain one or more custom parameters as defined in the Parameters subkey.</span></span> <span data-ttu-id="b5b4e-138">Пример: <code>https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&amp;role=present&amp;pw=%param3%</code></span><span class="sxs-lookup"><span data-stu-id="b5b4e-138">For example, <code>https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&amp;role=present&amp;pw=%param3%</code></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5b4e-139">сессионтипе</span><span class="sxs-lookup"><span data-stu-id="b5b4e-139">SessionType</span></span></p></td>
<td><p><span data-ttu-id="b5b4e-140">DWORD</span><span class="sxs-lookup"><span data-stu-id="b5b4e-140">DWORD</span></span></p></td>
<td><p><span data-ttu-id="b5b4e-141">0 = локальный сеанс.</span><span class="sxs-lookup"><span data-stu-id="b5b4e-141">0 = Local session.</span></span> <span data-ttu-id="b5b4e-142">Приложение запускается на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="b5b4e-142">The application is started on the local computer.</span></span></p>
<p><span data-ttu-id="b5b4e-143">1 = двусторонний сеанс (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="b5b4e-143">1 = Two-party session (default).</span></span> <span data-ttu-id="b5b4e-144">Lync 2013 запускает приложение локально, а затем отправляет системное уведомление другому пользователю.</span><span class="sxs-lookup"><span data-stu-id="b5b4e-144">Lync 2013 starts the application locally, and then sends a system notification to the other user.</span></span> <span data-ttu-id="b5b4e-145">Другой пользователь щелкает уведомление и запускает указанное приложение на своем компьютере.</span><span class="sxs-lookup"><span data-stu-id="b5b4e-145">The other user clicks the notification and starts the specified application on their computer.</span></span></p>
<p><span data-ttu-id="b5b4e-146">2 = многокомпонентный сеанс.</span><span class="sxs-lookup"><span data-stu-id="b5b4e-146">2 = Multiparty session.</span></span> <span data-ttu-id="b5b4e-147">Lync 2013 запускает приложение локально, а затем отправляет системные уведомления другим пользователям, предложи им запустить указанное приложение на своем компьютере.</span><span class="sxs-lookup"><span data-stu-id="b5b4e-147">Lync 2013 starts the application locally, and then sends system notifications to the other users, prompting them to start the specified application on their own computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5b4e-148">ексенсиблемену</span><span class="sxs-lookup"><span data-stu-id="b5b4e-148">ExensibleMenu</span></span></p></td>
<td><p><span data-ttu-id="b5b4e-149">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="b5b4e-149">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="b5b4e-150">Список меню, в котором будет отображаться эта команда, разделенных точкой с запятой.</span><span class="sxs-lookup"><span data-stu-id="b5b4e-150">A list of the menus where this command will appear, separated by semi-colons.</span></span> <span data-ttu-id="b5b4e-151">Возможные значения:</span><span class="sxs-lookup"><span data-stu-id="b5b4e-151">Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="b5b4e-152">маинвиндовактионс</span><span class="sxs-lookup"><span data-stu-id="b5b4e-152">MainWindowActions</span></span></p></li>
<li><p><span data-ttu-id="b5b4e-153">маинвиндовригхткликк</span><span class="sxs-lookup"><span data-stu-id="b5b4e-153">MainWindowRightClick</span></span></p></li>
<li><p><span data-ttu-id="b5b4e-154">конверсатионвиндовактионс</span><span class="sxs-lookup"><span data-stu-id="b5b4e-154">ConversationWindowActions</span></span></p></li>
<li><p><span data-ttu-id="b5b4e-155">конверсатионвиндовбуттон</span><span class="sxs-lookup"><span data-stu-id="b5b4e-155">ConversationWindowButton</span></span></p></li>
<li><p><span data-ttu-id="b5b4e-156">конверсатионвиндовригхткликк</span><span class="sxs-lookup"><span data-stu-id="b5b4e-156">ConversationWindowRightClick</span></span></p></li>
</ul>
<p><span data-ttu-id="b5b4e-157">Если Екстенсиблемену не определен, используются значения по умолчанию Маинвиндовригхткликк и Конверсатионвиндовактионс.</span><span class="sxs-lookup"><span data-stu-id="b5b4e-157">If ExtensibleMenu is not defined, the default values of MainWindowRightClick and ConversationWindowActions are used.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b5b4e-158">В следующей таблице описаны записи реестра для параметров.</span><span class="sxs-lookup"><span data-stu-id="b5b4e-158">The following table describes the registry entries for parameters.</span></span> <span data-ttu-id="b5b4e-159">Эти записи находятся на странице HKEY\_текущий\_пользователь\\,\\Microsoft\\Office\\15,0\\Lync\\сессионманажер\\параметры\\приложений.</span><span class="sxs-lookup"><span data-stu-id="b5b4e-159">These entries are place at HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters.</span></span>

### <a name="registry-entries-for-an-internet-based-collaboration-application"></a><span data-ttu-id="b5b4e-160">Записи реестра для приложения совместной работы на основе Интернета</span><span class="sxs-lookup"><span data-stu-id="b5b4e-160">Registry Entries for an Internet-based Collaboration Application</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b5b4e-161">Имя</span><span class="sxs-lookup"><span data-stu-id="b5b4e-161">Name</span></span></th>
<th><span data-ttu-id="b5b4e-162">Тип</span><span class="sxs-lookup"><span data-stu-id="b5b4e-162">Type</span></span></th>
<th><span data-ttu-id="b5b4e-163">Данные</span><span class="sxs-lookup"><span data-stu-id="b5b4e-163">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b5b4e-164">Параметр1</span><span class="sxs-lookup"><span data-stu-id="b5b4e-164">Param1</span></span></p></td>
<td><p><span data-ttu-id="b5b4e-165">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="b5b4e-165">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="b5b4e-166">Используется в маркерном формате (<code>%Parm1%</code>) для добавления значений, относящихся к пользователю, в раздел реестра оригинаторпас.</span><span class="sxs-lookup"><span data-stu-id="b5b4e-166">Used in tokenized format (<code>%Parm1%</code>) to add user-specific values to the OriginatorPath registry key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5b4e-167">Param2</span><span class="sxs-lookup"><span data-stu-id="b5b4e-167">Param2</span></span></p></td>
<td><p><span data-ttu-id="b5b4e-168">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="b5b4e-168">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="b5b4e-169">Обратитесь к разделу Param1.</span><span class="sxs-lookup"><span data-stu-id="b5b4e-169">See Param1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5b4e-170">Param3</span><span class="sxs-lookup"><span data-stu-id="b5b4e-170">Param3</span></span></p></td>
<td><p><span data-ttu-id="b5b4e-171">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="b5b4e-171">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="b5b4e-172">Обратитесь к разделу Param1.</span><span class="sxs-lookup"><span data-stu-id="b5b4e-172">See Param1.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b5b4e-173">В приведенном ниже примере параметры реестра интегрируют клиент ADatum для совместной работы с Lync 2013:</span><span class="sxs-lookup"><span data-stu-id="b5b4e-173">The following example registry settings integrate ADatum Collaboration Client with Lync 2013:</span></span>

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

## <a name="integrating-a-server-based-collaboration-application-with-lync-2013"></a><span data-ttu-id="b5b4e-174">Интеграция приложения для совместной работы на основе сервера с Lync 2013</span><span class="sxs-lookup"><span data-stu-id="b5b4e-174">Integrating a Server-Based Collaboration Application with Lync 2013</span></span>

<span data-ttu-id="b5b4e-175">Параметры добавления команд для запуска приложения совместной работы на основе сервера в Lync 2013 аналогичны тем, которые описаны в предыдущем разделе, интеграция приложения для совместной работы на основе Интернета с Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="b5b4e-175">The settings to add commands for starting a server-based collaboration application from within Lync 2013 are similar to those described in the previous section, Integrating an Internet-Based Collaboration Application with Lync 2013.</span></span> <span data-ttu-id="b5b4e-176">Однако Оригинаторпас не является обязательным, и некоторые значения изменяются.</span><span class="sxs-lookup"><span data-stu-id="b5b4e-176">However, the OriginatorPath is not required, and some values are changed.</span></span> <span data-ttu-id="b5b4e-177">Записи реестра размещаются в следующем расположении:</span><span class="sxs-lookup"><span data-stu-id="b5b4e-177">Registry entries are placed in the following location:</span></span>

  - <span data-ttu-id="b5b4e-178">Программное\_обеспечение\\\\для локального\\компьютера\\hKey\\\_параметры\\приложений\\\\Microsoft Office 15,0 Lync сессионманажер</span><span class="sxs-lookup"><span data-stu-id="b5b4e-178">HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters</span></span>

### <a name="registry-entries-for-a-server-based-collaboration-application"></a><span data-ttu-id="b5b4e-179">Записи реестра для приложения совместной работы на основе сервера</span><span class="sxs-lookup"><span data-stu-id="b5b4e-179">Registry Entries for a Server-based Collaboration Application</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b5b4e-180">Имя</span><span class="sxs-lookup"><span data-stu-id="b5b4e-180">Name</span></span></th>
<th><span data-ttu-id="b5b4e-181">Тип</span><span class="sxs-lookup"><span data-stu-id="b5b4e-181">Type</span></span></th>
<th><span data-ttu-id="b5b4e-182">Данные</span><span class="sxs-lookup"><span data-stu-id="b5b4e-182">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b5b4e-183">Имя</span><span class="sxs-lookup"><span data-stu-id="b5b4e-183">Name</span></span></p></td>
<td><p><span data-ttu-id="b5b4e-184">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="b5b4e-184">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="b5b4e-185">Имя приложения в том виде, в котором оно отображается в меню.</span><span class="sxs-lookup"><span data-stu-id="b5b4e-185">Name of the application as it appears on the menu.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5b4e-186">ApplicationType</span><span class="sxs-lookup"><span data-stu-id="b5b4e-186">ApplicationType</span></span></p></td>
<td><p><span data-ttu-id="b5b4e-187">DWORD</span><span class="sxs-lookup"><span data-stu-id="b5b4e-187">DWORD</span></span></p></td>
<td><p><span data-ttu-id="b5b4e-188">Значение = 1.</span><span class="sxs-lookup"><span data-stu-id="b5b4e-188">Value = 1.</span></span> <span data-ttu-id="b5b4e-189">Задает тип приложения "протокол".</span><span class="sxs-lookup"><span data-stu-id="b5b4e-189">Sets the application type to protocol.</span></span> <span data-ttu-id="b5b4e-190">Другие возможные значения в этом случае не применяются.</span><span class="sxs-lookup"><span data-stu-id="b5b4e-190">The other possible values do not apply in this case.</span></span> <span data-ttu-id="b5b4e-191">Если этот параметр отсутствует, Аппликатионтипе имеет значение 0 (исполняемый файл).</span><span class="sxs-lookup"><span data-stu-id="b5b4e-191">If not present, ApplicationType is set to 0 (executable).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5b4e-192">Path</span><span class="sxs-lookup"><span data-stu-id="b5b4e-192">Path</span></span></p></td>
<td><p><span data-ttu-id="b5b4e-193">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="b5b4e-193">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="b5b4e-194">Протокол, используемый для запуска приложения совместной работы.</span><span class="sxs-lookup"><span data-stu-id="b5b4e-194">Protocol used to start the collaboration application.</span></span> <span data-ttu-id="b5b4e-195">Для Live Meeting 2007 для параметра path задается значение <code>meet:%conf-uri%</code>.</span><span class="sxs-lookup"><span data-stu-id="b5b4e-195">For Live Meeting 2007, the value of Path is set to <code>meet:%conf-uri%</code>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5b4e-196">сессионтипе</span><span class="sxs-lookup"><span data-stu-id="b5b4e-196">SessionType</span></span></p></td>
<td><p><span data-ttu-id="b5b4e-197">DWORD</span><span class="sxs-lookup"><span data-stu-id="b5b4e-197">DWORD</span></span></p></td>
<td><p><span data-ttu-id="b5b4e-198">0 = локальный сеанс.</span><span class="sxs-lookup"><span data-stu-id="b5b4e-198">0 = Local session.</span></span> <span data-ttu-id="b5b4e-199">Приложение запускается на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="b5b4e-199">The application is started on the local computer.</span></span></p>
<p><span data-ttu-id="b5b4e-200">1 = двусторонний сеанс (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="b5b4e-200">1 = Two-party session (default).</span></span> <span data-ttu-id="b5b4e-201">Lync 2013 запускает приложение локально, а затем отправляет системное уведомление другому пользователю.</span><span class="sxs-lookup"><span data-stu-id="b5b4e-201">Lync 2013 starts the application locally, and then sends a system notification to the other user.</span></span> <span data-ttu-id="b5b4e-202">Другой пользователь щелкает уведомление и запускает указанное приложение на своем компьютере.</span><span class="sxs-lookup"><span data-stu-id="b5b4e-202">The other user clicks the notification and starts the specified application on their computer.</span></span></p>
<p><span data-ttu-id="b5b4e-203">2 = многокомпонентный сеанс.</span><span class="sxs-lookup"><span data-stu-id="b5b4e-203">2 = Multiparty session.</span></span> <span data-ttu-id="b5b4e-204">Lync 2013 запускает приложение локально, а затем отправляет системные уведомления другим пользователям, предложи им запустить указанное приложение на своем компьютере.</span><span class="sxs-lookup"><span data-stu-id="b5b4e-204">Lync 2013 starts the application locally, and then sends system notifications to the other users, prompting them to start the specified application on their computer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5b4e-205">мкутипе</span><span class="sxs-lookup"><span data-stu-id="b5b4e-205">MCUType</span></span></p></td>
<td><p><span data-ttu-id="b5b4e-206">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="b5b4e-206">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="b5b4e-207">DATA = тип сервера.</span><span class="sxs-lookup"><span data-stu-id="b5b4e-207">DATA = The type of server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5b4e-208">екстенсиблемену</span><span class="sxs-lookup"><span data-stu-id="b5b4e-208">ExtensibleMenu</span></span></p></td>
<td><p><span data-ttu-id="b5b4e-209">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="b5b4e-209">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="b5b4e-210">Список меню, в котором будет отображаться эта команда, разделенных точкой с запятой.</span><span class="sxs-lookup"><span data-stu-id="b5b4e-210">A list of the menus where this command will appear, separated by semicolons.</span></span> <span data-ttu-id="b5b4e-211">Возможные значения:</span><span class="sxs-lookup"><span data-stu-id="b5b4e-211">Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="b5b4e-212">маинвиндовактионс</span><span class="sxs-lookup"><span data-stu-id="b5b4e-212">MainWindowActions</span></span></p></li>
<li><p><span data-ttu-id="b5b4e-213">маинвиндовригхткликк</span><span class="sxs-lookup"><span data-stu-id="b5b4e-213">MainWindowRightClick</span></span></p></li>
<li><p><span data-ttu-id="b5b4e-214">конверсатионвиндовактионс</span><span class="sxs-lookup"><span data-stu-id="b5b4e-214">ConversationWindowActions</span></span></p></li>
<li><p><span data-ttu-id="b5b4e-215">конверсатионвиндовбуттон</span><span class="sxs-lookup"><span data-stu-id="b5b4e-215">ConversationWindowButton</span></span></p></li>
<li><p><span data-ttu-id="b5b4e-216">конверсатионвиндовригхткликк</span><span class="sxs-lookup"><span data-stu-id="b5b4e-216">ConversationWindowRightClick</span></span></p></li>
</ul>
<p><span data-ttu-id="b5b4e-217">Если Екстенсиблемену не определен, используются значения по умолчанию Маинвиндовригхткликк и Конверсатионвиндовактионс.</span><span class="sxs-lookup"><span data-stu-id="b5b4e-217">If ExtensibleMenu is not defined, the default values of MainWindowRightClick and ConversationWindowActions are used.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b5b4e-218">В следующем примере показано, как добавить команды для запуска клиента совместной работы ADatum из Lync 2013:</span><span class="sxs-lookup"><span data-stu-id="b5b4e-218">The following example adds commands to start ADatum Collaboration Client from within Lync 2013:</span></span>

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

