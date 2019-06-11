---
title: 'Lync Server 2013: Настройка нового доверенного сервера приложений'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure a new trusted application server
ms:assetid: a7233db7-fac3-43ff-972e-3bc29a56adb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg617964(v=OCS.15)
ms:contentKeyID: 48185085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4fc5a982724dd390ff97bf6dd4cad10f25572732
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841459"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-new-trusted-application-server-in-lync-server-2013"></a><span data-ttu-id="a1eb1-102">Настройка нового доверенного сервера приложений в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1eb1-102">Configure a new trusted application server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a1eb1-103">_**Тема последнего изменения:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="a1eb1-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="a1eb1-104">Надежное приложение — это приложение, основанное на API Microsoft Lync 2013 Server (УКМА 3,0), которое является надежным для Windows.</span><span class="sxs-lookup"><span data-stu-id="a1eb1-104">A trusted application is an application based on Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK that is trusted by Microsoft Lync Server 2013.</span></span> <span data-ttu-id="a1eb1-105">Подробнее об УКМА приложениях можно найти в [http://go.microsoft.com/fwlink/p/?linkId=210320](http://go.microsoft.com/fwlink/p/?linkid=210320)разделе "управляемая унифицированная связь API 3,0 Core SDK".</span><span class="sxs-lookup"><span data-stu-id="a1eb1-105">For details about UCMA applications, see “Unified Communications Managed API 3.0 Core SDK Documentation” at [http://go.microsoft.com/fwlink/p/?linkId=210320](http://go.microsoft.com/fwlink/p/?linkid=210320).</span></span>

<span data-ttu-id="a1eb1-106">Сведения о настройке Microsoft Outlook Web Access (OWA) и Lync Server 2013 можно найти в разделе "Настройка Outlook Web App и Lync Server 2010" в документации по Microsoft Exchange Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a1eb1-106">For information about configuring Microsoft Outlook Web Access (OWA) and Lync Server 2013, see “Configure Outlook Web App and Lync Server 2010 Integration” at the Microsoft Exchange Server 2013 documentation.</span></span>

<span data-ttu-id="a1eb1-107">Чтобы успешно публиковать, включать и отключать топологию при добавлении или удалении роли сервера, вы должны войти в систему как пользователь, который является членом группы администраторов Рткуниверсалсерверадминс и domain.</span><span class="sxs-lookup"><span data-stu-id="a1eb1-107">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged on as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="a1eb1-108">Кроме того, можно делегировать права администратора и права на Добавление ролей сервера.</span><span class="sxs-lookup"><span data-stu-id="a1eb1-108">It is also possible to delegate the proper administrator permissions and rights for adding server roles.</span></span> <span data-ttu-id="a1eb1-109">Дополнительные сведения можно найти [в разделе Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="a1eb1-109">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in the Deployment documentation.</span></span> <span data-ttu-id="a1eb1-110">Для других изменений конфигурации требуется только членство в группе Рткуниверсалсерверадминс.</span><span class="sxs-lookup"><span data-stu-id="a1eb1-110">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

<div>

## <a name="to-configure-a-trusted-application-server"></a><span data-ttu-id="a1eb1-111">Настройка доверенного сервера приложений</span><span class="sxs-lookup"><span data-stu-id="a1eb1-111">To configure a trusted application server</span></span>

1.  <span data-ttu-id="a1eb1-112">Войдите на компьютер, где установлен построитель топологий, с использованием учетной записи, входящей в группу администраторов домена и группу RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="a1eb1-112">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="a1eb1-113">Запустить построитель топологии: нажмите кнопку **Пуск**, выберите пункт **все программы**, а затем — **Microsoft Lync Server 2013**и нажмите кнопку Построитель **топологии Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="a1eb1-113">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

3.  <span data-ttu-id="a1eb1-114">Выберите пункт **топология скачивания из существующего развертывания**и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a1eb1-114">Select **Download topology from existing deployment**, and then click **OK**.</span></span>

4.  <span data-ttu-id="a1eb1-115">В диалоговом окне **Сохранить топологию как** выберите нужный файл в построителе топологии, а затем нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="a1eb1-115">In the **Save Topology As** dialog box, click the Topology Builder file you want to use, and then click **Save**.</span></span>

5.  <span data-ttu-id="a1eb1-116">На левой панели щелкните правой кнопкой мыши **Доверенные серверы приложений**и выберите команду **создать доверенный пул приложений**.</span><span class="sxs-lookup"><span data-stu-id="a1eb1-116">In the left pane, right-click **Trusted application servers**, and then click **New Trusted Application Pool**.</span></span>

6.  <span data-ttu-id="a1eb1-117">Введите **полное доменное имя пула** для доверенного пула приложений, укажите, будет ли он одним или несколькими серверами, и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="a1eb1-117">Enter the **Pool FQDN** of the trusted application pool, select whether it will be a single-server or multiple-server, and then click **Next**.</span></span>

7.  <span data-ttu-id="a1eb1-118">На странице **Выбор следующего прыжка** в списке выберите пул внешних интерфейсов Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a1eb1-118">On the **Select the next hop** page, from the list, select the Lync Server 2013 Front End pool.</span></span>

8.  <span data-ttu-id="a1eb1-119">Нажмите **Готово**.</span><span class="sxs-lookup"><span data-stu-id="a1eb1-119">Click **Finish**.</span></span>

9.  <span data-ttu-id="a1eb1-120">Выберите верхний узел **Lync Server 2013**, а затем в меню **действия** выберите пункт **топология публикации**.</span><span class="sxs-lookup"><span data-stu-id="a1eb1-120">Select the top node **Lync Server 2013**, and then, from the **Actions** menu, click **Publish Topology**.</span></span>
    
    <span data-ttu-id="a1eb1-121">**Надежное приложение пула приложений** должно быть успешно создано и связано с правильным пулом переднего плана.</span><span class="sxs-lookup"><span data-stu-id="a1eb1-121">The **Trusted Application Pool** should have been created successfully and associated with the correct Front End pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

