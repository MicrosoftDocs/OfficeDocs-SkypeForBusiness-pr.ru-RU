---
title: Конфигурация страницы присоединения к собранию
ms.reviewer: ''
ms.author: kenwith
author: kenwith
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
ms.openlocfilehash: 104f5a06395de236c280d083e6211decaaa62b35
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728159"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-meeting-join-page"></a><span data-ttu-id="a53cf-102">Конфигурация страницы присоединения к собранию</span><span class="sxs-lookup"><span data-stu-id="a53cf-102">Configure the meeting join page</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a53cf-103">_**Тема последнего изменения:** 2012-12-14_</span><span class="sxs-lookup"><span data-stu-id="a53cf-103">_**Topic Last Modified:** 2012-12-14_</span></span>

<span data-ttu-id="a53cf-104">Когда пользователь щелкает ссылку на собрание в приглашении на собрание, страница присоединения к собранию определяет, уже установлен ли клиент Lync 2013 на компьютере пользователя.</span><span class="sxs-lookup"><span data-stu-id="a53cf-104">When a user clicks a meeting link in a meeting request, the meeting join page detects whether a Lync 2013 client is already installed on the user’s computer.</span></span> <span data-ttu-id="a53cf-105">Если клиент уже установлен, этот клиент открывает и присоединяется к собранию.</span><span class="sxs-lookup"><span data-stu-id="a53cf-105">If a client is already installed, that client opens and joins the meeting.</span></span> <span data-ttu-id="a53cf-106">Если клиент не установлен, по умолчанию открывается версия 2013 Microsoft Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="a53cf-106">If a client is not installed, by default the 2013 version of Microsoft Lync Web App opens.</span></span>

<span data-ttu-id="a53cf-107">Вы можете изменить поведение страницы присоединения к собранию, если вы хотите разрешить пользователям присоединяться к собраниям с помощью Office Communicator 2007 R2 или Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="a53cf-107">You can modify the behavior of the meeting join page if you want to allow users to join meetings with Office Communicator 2007 R2 or Lync 2010 Attendant.</span></span> <span data-ttu-id="a53cf-108">Эти параметры конфигурации были удалены из панели управления Lync Server 2013, но их можно настроить с помощью командлета Ксвебсервицеконфигуратион.</span><span class="sxs-lookup"><span data-stu-id="a53cf-108">These configuration options have been removed from the Lync Server 2013 Control Panel, but you configure them by using the CsWebServiceConfiguration cmdlet.</span></span>

### <a name="meeting-join-page-cswebserviceconfiguration-parameters"></a><span data-ttu-id="a53cf-109">Параметры Ксвебсервицеконфигуратион на странице присоединения к собранию</span><span class="sxs-lookup"><span data-stu-id="a53cf-109">Meeting Join Page CsWebServiceConfiguration Parameters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a53cf-110">Параметр Ксвебсервицеконфигуратион</span><span class="sxs-lookup"><span data-stu-id="a53cf-110">CsWebServiceConfiguration Parameter</span></span></th>
<th><span data-ttu-id="a53cf-111">Описание</span><span class="sxs-lookup"><span data-stu-id="a53cf-111">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a53cf-112">шовжоинусинглегациклиентлинк</span><span class="sxs-lookup"><span data-stu-id="a53cf-112">ShowJoinUsingLegacyClientLink</span></span></p></td>
<td><p><span data-ttu-id="a53cf-113">Если установлено значение true, пользователи, присоединяющиеся к собранию с помощью клиентского приложения, отличного от Lync, получают возможность присоединиться к собранию с помощью Office Communicator 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="a53cf-113">If set to True, users joining a meeting by using a client application other than Lync will be given the opportunity to join the meeting by using Office Communicator 2007 R2.</span></span> <span data-ttu-id="a53cf-114">Значение по умолчанию — False.</span><span class="sxs-lookup"><span data-stu-id="a53cf-114">The default value is False.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a53cf-115">шовалтернатежоиноптионсекспандед</span><span class="sxs-lookup"><span data-stu-id="a53cf-115">ShowAlternateJoinOptionsExpanded</span></span></p></td>
<td><p><span data-ttu-id="a53cf-116">Если установлено значение true, дополнительные параметры для присоединения к онлайн-конференции (например, Office Communicator 2007 R2) автоматически развертываются и появятся для пользователей.</span><span class="sxs-lookup"><span data-stu-id="a53cf-116">When set to True then alternate options for joining an online conference (such as Office Communicator 2007 R2) will automatically be expanded and shown to users.</span></span> <span data-ttu-id="a53cf-117">Если задано значение false (по умолчанию), эти параметры будут доступны, но пользователю потребуется отобразить список параметров.</span><span class="sxs-lookup"><span data-stu-id="a53cf-117">When set to False (the default value) these options will be available, but the user will have to display the list of options for themselves.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-the-meeting-join-page-by-using-lync-server-2013-management-shell"></a><span data-ttu-id="a53cf-118">Настройка страницы присоединения к собранию с помощью управляющей оболочки Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a53cf-118">To configure the meeting join page by using Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="a53cf-119">Запустите командную консоль Lync Server 2013: нажмите кнопку **Пуск**, выберите пункт **все программы**, а затем — **Microsoft Lync Server 2013**и щелкните **Командная консоль управления Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="a53cf-119">Start the Lync Server 2013 Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="a53cf-120">Выполнить следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="a53cf-120">Run the following cmdlet:</span></span>
    
        Get-CsWebServiceConfiguration
    
    <span data-ttu-id="a53cf-121">Этот командлет возвращает параметры конфигурации веб-службы.</span><span class="sxs-lookup"><span data-stu-id="a53cf-121">This cmdlet returns the web service configuration settings.</span></span>

3.  <span data-ttu-id="a53cf-122">Выполните следующую команду, указав для параметров значение истина или ложь, в зависимости от вашего предпочтения (Дополнительные сведения о параметрах этого командлета можно найти в документации по среде управления Lync Server 2013).</span><span class="sxs-lookup"><span data-stu-id="a53cf-122">Run the following command, with the parameters set to True or False, depending on your preference (for details about the parameters for this cmdlet, see the Lync Server 2013 Management Shell documentation):</span></span>
    
        Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True

</div>

</div>

<span> </span>

</div>

</div>

</div>

