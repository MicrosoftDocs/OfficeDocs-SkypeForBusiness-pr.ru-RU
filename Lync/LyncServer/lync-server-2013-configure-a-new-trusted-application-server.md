---
title: 'Lync Server 2013: Настройка нового доверенного сервера приложений'
description: 'Lync Server 2013: Настройка нового сервера доверенных приложений.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a new trusted application server
ms:assetid: a7233db7-fac3-43ff-972e-3bc29a56adb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg617964(v=OCS.15)
ms:contentKeyID: 48185085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f3cc13c747c5755297b01ae36f27f06d19591acc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552125"
---
# <a name="configure-a-new-trusted-application-server-in-lync-server-2013"></a><span data-ttu-id="28e29-103">Настройка нового доверенного сервера приложений в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="28e29-103">Configure a new trusted application server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="28e29-104">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="28e29-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="28e29-105">Доверенное приложение — это приложение, основанное на Microsoft Lync Server Managed Communications Managed API (UCMA) 3,0 Core SDK, которому доверяет Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="28e29-105">A trusted application is an application based on Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK that is trusted by Microsoft Lync Server 2013.</span></span> <span data-ttu-id="28e29-106">Подробные сведения о приложениях UCMA можно найти в разделе "интегрированный API Managed Communications API 3,0" [https://go.microsoft.com/fwlink/p/?linkId=210320](https://go.microsoft.com/fwlink/p/?linkid=210320) .</span><span class="sxs-lookup"><span data-stu-id="28e29-106">For details about UCMA applications, see “Unified Communications Managed API 3.0 Core SDK Documentation” at [https://go.microsoft.com/fwlink/p/?linkId=210320](https://go.microsoft.com/fwlink/p/?linkid=210320).</span></span>

<span data-ttu-id="28e29-107">Сведения о настройке Microsoft Outlook Web Access (OWA) и Lync Server 2013 приведены в статье "Настройка Outlook Web App и интеграции Lync Server 2010" в документации по Microsoft Exchange Server 2013.</span><span class="sxs-lookup"><span data-stu-id="28e29-107">For information about configuring Microsoft Outlook Web Access (OWA) and Lync Server 2013, see “Configure Outlook Web App and Lync Server 2010 Integration” at the Microsoft Exchange Server 2013 documentation.</span></span>

<span data-ttu-id="28e29-108">Чтобы успешно опубликовать, включить или отключить топологию при добавлении или удалении роли сервера, необходимо войти в систему с учетной записью члена групп RTCUniversalServerAdmins или "Администраторы домена".</span><span class="sxs-lookup"><span data-stu-id="28e29-108">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged on as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="28e29-109">Кроме того, вы можете делегировать соответствующие разрешения и права администратора для добавления ролей сервера.</span><span class="sxs-lookup"><span data-stu-id="28e29-109">It is also possible to delegate the proper administrator permissions and rights for adding server roles.</span></span> <span data-ttu-id="28e29-110">Для получения дополнительных сведений обратитесь к разделу [Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="28e29-110">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in the Deployment documentation.</span></span> <span data-ttu-id="28e29-111">Для остальных изменений конфигурации требуется только членство в группе RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="28e29-111">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

<div>

## <a name="to-configure-a-trusted-application-server"></a><span data-ttu-id="28e29-112">Настройка сервера доверенных приложений</span><span class="sxs-lookup"><span data-stu-id="28e29-112">To configure a trusted application server</span></span>

1.  <span data-ttu-id="28e29-113">Войдите в систему компьютера, на котором построитель топологий установлен как член группы администраторов доменов и группы RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="28e29-113">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="28e29-114">Запустите построитель топологий: нажмите кнопку **Пуск**, последовательно выберите пункты **все программы**, **Microsoft Lync Server 2013**и **Построитель топологий Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="28e29-114">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

3.  <span data-ttu-id="28e29-115">Выберите **Download topology from existing deployment** (Загрузить топологию из существующего развертывания) и затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="28e29-115">Select **Download topology from existing deployment**, and then click **OK**.</span></span>

4.  <span data-ttu-id="28e29-116">В диалоговом окне **Сохранить топологию как** выберите нужный файл в построителе топологий, а затем нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="28e29-116">In the **Save Topology As** dialog box, click the Topology Builder file you want to use, and then click **Save**.</span></span>

5.  <span data-ttu-id="28e29-117">В области слева щелкните правой кнопкой мыши пункт **Серверы доверенных приложений** и выберите команду **Создать пул доверенных приложений**.</span><span class="sxs-lookup"><span data-stu-id="28e29-117">In the left pane, right-click **Trusted application servers**, and then click **New Trusted Application Pool**.</span></span>

6.  <span data-ttu-id="28e29-118">В поле **Pool FQDN** (Полное доменное имя пула) введите полное доменное имя пула доверенных приложений, укажите параметры пула (пул из одного компьютера или нескольких компьютеров) и затем нажмите кнопку **Next** (Далее).</span><span class="sxs-lookup"><span data-stu-id="28e29-118">Enter the **Pool FQDN** of the trusted application pool, select whether it will be a single-server or multiple-server, and then click **Next**.</span></span>

7.  <span data-ttu-id="28e29-119">На странице **Выбор следующего прыжка** в списке выберите пул переднего плана Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="28e29-119">On the **Select the next hop** page, from the list, select the Lync Server 2013 Front End pool.</span></span>

8.  <span data-ttu-id="28e29-120">Нажмите кнопку **Finish** (Готово).</span><span class="sxs-lookup"><span data-stu-id="28e29-120">Click **Finish**.</span></span>

9.  <span data-ttu-id="28e29-121">Выберите верхний узел **Lync Server 2013** и затем в меню **Действия** выберите пункт **Опубликовать**.</span><span class="sxs-lookup"><span data-stu-id="28e29-121">Select the top node **Lync Server 2013**, and then, from the **Actions** menu, click **Publish Topology**.</span></span>
    
    <span data-ttu-id="28e29-122">**Пул доверенных приложений** успешно создан и связан с соответствующим интерфейсным пулом.</span><span class="sxs-lookup"><span data-stu-id="28e29-122">The **Trusted Application Pool** should have been created successfully and associated with the correct Front End pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

