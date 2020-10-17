---
title: 'Lync Server 2013: отключение обхода сетевых носителей'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disabling network media bypass
ms:assetid: 936d2678-d712-4589-b172-b5793013652f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688141(v=OCS.15)
ms:contentKeyID: 49733741
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 29508180b54ace29e1ac913dd52d06d374068bfc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528986"
---
# <a name="disabling-network-media-bypass-in-lync-server-2013"></a><span data-ttu-id="1ce21-102">Отключение обхода сетевых носителей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ce21-102">Disabling network media bypass in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ce21-103">_**Последнее изменение темы:** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="1ce21-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="1ce21-104">Параметры обхода сервера мультимедиа применяются глобально в развертывании Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1ce21-104">Media bypass settings apply globally across a Microsoft Lync Server 2013 deployment.</span></span> <span data-ttu-id="1ce21-105">Обход сервера-посредника позволяет звонкам обходить сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="1ce21-105">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="1ce21-106">Сведения о том, когда следует использовать обход сервера мультимедиа, приведены в разделе [Планирование обхода сервера мультимедиа в Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) в разделе Планирование. Вы можете отключить обход сервера мультимедиа в панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1ce21-106">For details about when to use Media bypass, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) in the Planning section.You can disable media bypass from the Lync Server Control Panel.</span></span> <span data-ttu-id="1ce21-107">Дополнительные сведения о включении и настройке Медиал обхода можно найти [в статье Включение обхода сетевых носителей в Lync Server 2013](lync-server-2013-enabling-network-media-bypass.md)</span><span class="sxs-lookup"><span data-stu-id="1ce21-107">For details on enabling and configuring medial bypass, see [Enabling network media bypass in Lync Server 2013](lync-server-2013-enabling-network-media-bypass.md)</span></span>

<div>

## <a name="to-disable-media-bypass"></a><span data-ttu-id="1ce21-108">Отключение обхода медиаданных</span><span class="sxs-lookup"><span data-stu-id="1ce21-108">To disable media bypass</span></span>

1.  <span data-ttu-id="1ce21-109">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="1ce21-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1ce21-110">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1ce21-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1ce21-111">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="1ce21-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1ce21-112">На панели навигации слева выберите пункт **Конфигурация сети** и щелкните **Глобальная**.</span><span class="sxs-lookup"><span data-stu-id="1ce21-112">In the left navigation bar, click **Network Configuration** and then click **Global**.</span></span>

4.  <span data-ttu-id="1ce21-p103">На странице **Глобальная** выберите конфигурацию **Глобальная**. На этой странице всегда приводится только одна конфигурация, и она всегда имеет название "Глобальная".</span><span class="sxs-lookup"><span data-stu-id="1ce21-p103">On the **Global** page, click the **Global** configuration. There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="1ce21-115">В меню **Изменить** щелкните **Просмотреть сведения**.</span><span class="sxs-lookup"><span data-stu-id="1ce21-115">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="1ce21-116">На странице **Изменить глобальную настройку** снимите флажок **Разрешить обход мультимедиа**.</span><span class="sxs-lookup"><span data-stu-id="1ce21-116">On the **Edit Global Setting** page, clear the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="1ce21-117">Щелкните **Сохранить**, чтобы сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="1ce21-117">Click **Commit** to save your changes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1ce21-118">См. также</span><span class="sxs-lookup"><span data-stu-id="1ce21-118">See Also</span></span>


[<span data-ttu-id="1ce21-119">Включение обхода сетевых носителей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ce21-119">Enabling network media bypass in Lync Server 2013</span></span>](lync-server-2013-enabling-network-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

