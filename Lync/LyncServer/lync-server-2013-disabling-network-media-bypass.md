---
title: 'Lync Server 2013: отключение обхода сетевых мультимедийных файлов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Disabling network media bypass
ms:assetid: 936d2678-d712-4589-b172-b5793013652f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688141(v=OCS.15)
ms:contentKeyID: 49733741
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a9bfab9fbf8174a1124a45681098196c84ac5444
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834377"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disabling-network-media-bypass-in-lync-server-2013"></a><span data-ttu-id="c2db9-102">Отключение обхода сетевых мультимедийных файлов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c2db9-102">Disabling network media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c2db9-103">_**Тема последнего изменения:** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="c2db9-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="c2db9-104">Параметры обхода мультимедиа применяются глобально в рамках развертывания Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c2db9-104">Media bypass settings apply globally across a Microsoft Lync Server 2013 deployment.</span></span> <span data-ttu-id="c2db9-105">Обойти функцию мультимедиа позволяет обходить сервер.</span><span class="sxs-lookup"><span data-stu-id="c2db9-105">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="c2db9-106">Сведения о том, когда следует использовать обход мультимедиа, приведены в статье [Планирование обхода мультимедиа в Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) в разделе Планирование. Вы можете отключить обход мультимедиа с помощью панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c2db9-106">For details about when to use Media bypass, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) in the Planning section.You can disable media bypass from the Lync Server Control Panel.</span></span> <span data-ttu-id="c2db9-107">Дополнительные сведения о включении и настройке Медиал обхода можно найти [в разделе Включение обхода сетевого мультимедиа в Lync Server 2013](lync-server-2013-enabling-network-media-bypass.md)</span><span class="sxs-lookup"><span data-stu-id="c2db9-107">For details on enabling and configuring medial bypass, see [Enabling network media bypass in Lync Server 2013](lync-server-2013-enabling-network-media-bypass.md)</span></span>

<div>

## <a name="to-disable-media-bypass"></a><span data-ttu-id="c2db9-108">Отключение обхода мультимедиа</span><span class="sxs-lookup"><span data-stu-id="c2db9-108">To disable media bypass</span></span>

1.  <span data-ttu-id="c2db9-109">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="c2db9-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c2db9-110">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c2db9-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c2db9-111">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c2db9-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c2db9-112">На панели навигации слева выберите пункт **Конфигурация сети** , а затем — **Глобальная**.</span><span class="sxs-lookup"><span data-stu-id="c2db9-112">In the left navigation bar, click **Network Configuration** and then click **Global**.</span></span>

4.  <span data-ttu-id="c2db9-113">На **глобальной** странице щелкните глобальную конфигурацию \*\*\*\* .</span><span class="sxs-lookup"><span data-stu-id="c2db9-113">On the **Global** page, click the **Global** configuration.</span></span> <span data-ttu-id="c2db9-114">Всегда существует только одна конфигурация, и она всегда имеет имя Global.</span><span class="sxs-lookup"><span data-stu-id="c2db9-114">There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="c2db9-115">В меню **Правка** выберите команду **Просмотреть сведения**.</span><span class="sxs-lookup"><span data-stu-id="c2db9-115">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="c2db9-116">На странице **изменение глобальных параметров** снимите флажок **включить обход мультимедиа** .</span><span class="sxs-lookup"><span data-stu-id="c2db9-116">On the **Edit Global Setting** page, clear the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="c2db9-117">Нажмите \*\*\*\* кнопку Сохранить, чтобы сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="c2db9-117">Click **Commit** to save your changes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c2db9-118">См. также</span><span class="sxs-lookup"><span data-stu-id="c2db9-118">See Also</span></span>


[<span data-ttu-id="c2db9-119">Включение обхода сетевых мультимедийных файлов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c2db9-119">Enabling network media bypass in Lync Server 2013</span></span>](lync-server-2013-enabling-network-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

