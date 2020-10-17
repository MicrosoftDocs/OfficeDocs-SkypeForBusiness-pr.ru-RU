---
title: Конфигурация страницы присоединения к собранию
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure the meeting join page
ms:assetid: a87319b7-3124-4262-8f9d-18138870ee2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205145(v=OCS.15)
ms:contentKeyID: 48185030
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 464b690709444c540d9a1b06809a751b5b15d82a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503316"
---
# <a name="configure-the-meeting-join-page"></a><span data-ttu-id="43233-102">Конфигурация страницы присоединения к собранию</span><span class="sxs-lookup"><span data-stu-id="43233-102">Configure the meeting join page</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="43233-103">_**Последнее изменение темы:** 2012-12-14_</span><span class="sxs-lookup"><span data-stu-id="43233-103">_**Topic Last Modified:** 2012-12-14_</span></span>

<span data-ttu-id="43233-104">Когда пользователь щелкает ссылку на собрание в приглашении на собрание, страница присоединения к собранию определяет, установлен ли клиент Lync 2013 на компьютере пользователя.</span><span class="sxs-lookup"><span data-stu-id="43233-104">When a user clicks a meeting link in a meeting request, the meeting join page detects whether a Lync 2013 client is already installed on the user’s computer.</span></span> <span data-ttu-id="43233-105">Если клиент уже установлен, он открывается и выполняет присоединение к собранию.</span><span class="sxs-lookup"><span data-stu-id="43233-105">If a client is already installed, that client opens and joins the meeting.</span></span> <span data-ttu-id="43233-106">Если клиент не установлен, по умолчанию открывается версия Microsoft Lync Web App 2013.</span><span class="sxs-lookup"><span data-stu-id="43233-106">If a client is not installed, by default the 2013 version of Microsoft Lync Web App opens.</span></span>

<span data-ttu-id="43233-107">Вы можете изменить поведение страницы присоединения к собранию, если хотите разрешить пользователям присоединяться к собраниям с помощью Office Communicator 2007 R2 или Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="43233-107">You can modify the behavior of the meeting join page if you want to allow users to join meetings with Office Communicator 2007 R2 or Lync 2010 Attendant.</span></span> <span data-ttu-id="43233-108">Эти параметры конфигурации были удалены из панели управления Lync Server 2013, но их можно настроить с помощью командлета CsWebServiceConfiguration.</span><span class="sxs-lookup"><span data-stu-id="43233-108">These configuration options have been removed from the Lync Server 2013 Control Panel, but you configure them by using the CsWebServiceConfiguration cmdlet.</span></span>

### <a name="meeting-join-page-cswebserviceconfiguration-parameters"></a><span data-ttu-id="43233-109">Параметры командлета CsWebServiceConfiguration для настройки страницы присоединения к собранию</span><span class="sxs-lookup"><span data-stu-id="43233-109">Meeting Join Page CsWebServiceConfiguration Parameters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="43233-110">Параметр командлета CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="43233-110">CsWebServiceConfiguration Parameter</span></span></th>
<th><span data-ttu-id="43233-111">Описание</span><span class="sxs-lookup"><span data-stu-id="43233-111">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="43233-112">шовжоинусинглегациклиентлинк</span><span class="sxs-lookup"><span data-stu-id="43233-112">ShowJoinUsingLegacyClientLink</span></span></p></td>
<td><p><span data-ttu-id="43233-113">Если задано значение true, пользователи, присоединяющиеся к собранию с помощью клиентского приложения, отличного от Lync, получают возможность присоединиться к собранию с помощью Office Communicator 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="43233-113">If set to True, users joining a meeting by using a client application other than Lync will be given the opportunity to join the meeting by using Office Communicator 2007 R2.</span></span> <span data-ttu-id="43233-114">Значение по умолчанию — False.</span><span class="sxs-lookup"><span data-stu-id="43233-114">The default value is False.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43233-115">шовалтернатежоиноптионсекспандед</span><span class="sxs-lookup"><span data-stu-id="43233-115">ShowAlternateJoinOptionsExpanded</span></span></p></td>
<td><p><span data-ttu-id="43233-p104">Если параметр имеет значение True, то альтернативные параметры присоединения к конференции по сети (например, Office Communicator 2007 R2) будут отображаться автоматически. Если параметр имеет значение False (значение по умолчанию), эти параметры будут доступны, но пользователям придется самостоятельно открывать список параметров.</span><span class="sxs-lookup"><span data-stu-id="43233-p104">When set to True then alternate options for joining an online conference (such as Office Communicator 2007 R2) will automatically be expanded and shown to users. When set to False (the default value) these options will be available, but the user will have to display the list of options for themselves.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-the-meeting-join-page-by-using-lync-server-2013-management-shell"></a><span data-ttu-id="43233-118">Настройка страницы присоединения к собранию с помощью консоли управления Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="43233-118">To configure the meeting join page by using Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="43233-119">Запустите командную консоль Lync Server 2013: нажмите кнопку **Пуск**, выберите **все программы**, **Microsoft Lync Server 2013**и щелкните **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="43233-119">Start the Lync Server 2013 Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="43233-120">Выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="43233-120">Run the following cmdlet:</span></span>
    
        Get-CsWebServiceConfiguration
    
    <span data-ttu-id="43233-121">Этот командлет возвращает параметры конфигурации веб-службы.</span><span class="sxs-lookup"><span data-stu-id="43233-121">This cmdlet returns the web service configuration settings.</span></span>

3.  <span data-ttu-id="43233-122">Выполните следующую команду, указав для параметров значение true или false, в зависимости от вашего предпочтения (Дополнительные сведения о параметрах для этого командлета приведены в документации по среде управления Lync Server 2013).</span><span class="sxs-lookup"><span data-stu-id="43233-122">Run the following command, with the parameters set to True or False, depending on your preference (for details about the parameters for this cmdlet, see the Lync Server 2013 Management Shell documentation):</span></span>
    
        Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True

</div>

</div>

<span> </span>

</div>

</div>

</div>

