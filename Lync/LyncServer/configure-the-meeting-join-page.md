---
title: Конфигурация страницы присоединения к собранию
description: Настройка страницы присоединения к собранию.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure the meeting join page
ms:assetid: 036c9d03-ad95-4d63-a3d8-6cae1a8ad530
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204635(v=OCS.15)
ms:contentKeyID: 48183260
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af49a57a6844c59bf6f6631d996d8efe12152c52
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542965"
---
# <a name="configure-the-meeting-join-page"></a><span data-ttu-id="e8562-103">Конфигурация страницы присоединения к собранию</span><span class="sxs-lookup"><span data-stu-id="e8562-103">Configure the meeting join page</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e8562-104">_**Последнее изменение темы:** 2012-12-14_</span><span class="sxs-lookup"><span data-stu-id="e8562-104">_**Topic Last Modified:** 2012-12-14_</span></span>

<span data-ttu-id="e8562-105">Когда пользователь щелкает ссылку на собрание в приглашении на собрание, страница присоединения к собранию определяет, установлен ли клиент Lync 2013 на компьютере пользователя.</span><span class="sxs-lookup"><span data-stu-id="e8562-105">When a user clicks a meeting link in a meeting request, the meeting join page detects whether a Lync 2013 client is already installed on the user’s computer.</span></span> <span data-ttu-id="e8562-106">Если клиент уже установлен, он открывается и выполняет присоединение к собранию.</span><span class="sxs-lookup"><span data-stu-id="e8562-106">If a client is already installed, that client opens and joins the meeting.</span></span> <span data-ttu-id="e8562-107">Если клиент не установлен, по умолчанию открывается версия Lync Web App 2013.</span><span class="sxs-lookup"><span data-stu-id="e8562-107">If a client is not installed, by default the 2013 version of Lync Web App opens.</span></span>

<span data-ttu-id="e8562-108">Вы можете изменить поведение страницы присоединения к собранию, если хотите разрешить пользователям присоединяться к собраниям с помощью Office Communicator 2007 R2 или Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="e8562-108">You can modify the behavior of the meeting join page if you want to allow users to join meetings with Office Communicator 2007 R2 or Lync 2010 Attendant.</span></span> <span data-ttu-id="e8562-109">Эти параметры конфигурации были удалены из панели управления Lync Server 2013, но их можно настроить с помощью командлета CsWebServiceConfiguration.</span><span class="sxs-lookup"><span data-stu-id="e8562-109">These configuration options have been removed from the Lync Server 2013 Control Panel, but you configure them by using the CsWebServiceConfiguration cmdlet.</span></span>

### <a name="meeting-join-page-cswebserviceconfiguration-parameters"></a><span data-ttu-id="e8562-110">Параметры командлета CsWebServiceConfiguration для настройки страницы присоединения к собранию</span><span class="sxs-lookup"><span data-stu-id="e8562-110">Meeting Join Page CsWebServiceConfiguration Parameters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e8562-111">Параметр командлета CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="e8562-111">CsWebServiceConfiguration Parameter</span></span></th>
<th><span data-ttu-id="e8562-112">Описание</span><span class="sxs-lookup"><span data-stu-id="e8562-112">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e8562-113">шовжоинусинглегациклиентлинк</span><span class="sxs-lookup"><span data-stu-id="e8562-113">ShowJoinUsingLegacyClientLink</span></span></p></td>
<td><p><span data-ttu-id="e8562-114">Если задано значение true, пользователи, присоединяющиеся к собранию с помощью клиентского приложения, отличного от Lync, получают возможность присоединиться к собранию с помощью Office Communicator 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e8562-114">If set to True, users joining a meeting by using a client application other than Lync will be given the opportunity to join the meeting by using Office Communicator 2007 R2.</span></span> <span data-ttu-id="e8562-115">Значение по умолчанию — False.</span><span class="sxs-lookup"><span data-stu-id="e8562-115">The default value is False.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8562-116">шовалтернатежоиноптионсекспандед</span><span class="sxs-lookup"><span data-stu-id="e8562-116">ShowAlternateJoinOptionsExpanded</span></span></p></td>
<td><p><span data-ttu-id="e8562-p104">Если параметр имеет значение True, то альтернативные параметры присоединения к конференции по сети (например, Office Communicator 2007 R2) будут отображаться автоматически. Если параметр имеет значение False (значение по умолчанию), эти параметры будут доступны, но пользователям придется самостоятельно открывать список параметров.</span><span class="sxs-lookup"><span data-stu-id="e8562-p104">When set to True then alternate options for joining an online conference (such as Office Communicator 2007 R2) will automatically be expanded and shown to users. When set to False (the default value) these options will be available, but the user will have to display the list of options for themselves.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-the-meeting-join-page-by-using-lync-server-2013-management-shell"></a><span data-ttu-id="e8562-119">Настройка страницы присоединения к собранию с помощью консоли управления Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8562-119">To configure the meeting join page by using Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="e8562-120">Запустите командную консоль Lync Server 2013: нажмите кнопку **Пуск**, выберите **все программы**, **Microsoft Lync Server 2013**и щелкните **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="e8562-120">Start the Lync Server 2013 Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="e8562-121">Выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="e8562-121">Run the following cmdlet:</span></span>
    
        Get-CsWebServiceConfiguration
    
    <span data-ttu-id="e8562-122">Этот командлет возвращает параметры конфигурации веб-службы.</span><span class="sxs-lookup"><span data-stu-id="e8562-122">This cmdlet returns the web service configuration settings.</span></span>

3.  <span data-ttu-id="e8562-123">Выполните следующую команду, указав для параметров значение true или false, в зависимости от вашего предпочтения (Дополнительные сведения о параметрах для этого командлета приведены в документации по среде управления Lync Server 2013).</span><span class="sxs-lookup"><span data-stu-id="e8562-123">Run the following command, with the parameters set to True or False, depending on your preference (for details about the parameters for this cmdlet, see the Lync Server 2013 Management Shell documentation):</span></span>
    
        Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True

</div>

</div>

<span> </span>

</div>

</div>

</div>

