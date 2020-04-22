---
title: 'Lync Server 2013: Примечание о подключении Lync — Skype для Lync в'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Note about Lync-Skype connectivity for Lync On
ms:assetid: 1d0f5c1a-74c6-468f-9877-ad2b1ddf355f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440169(v=OCS.15)
ms:contentKeyID: 57793359
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de54cbdde864da5600c06b608344e8593529d604
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780708"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="note-about-lync-skype-connectivity-in-lync-server-2013-for-lync-online-customers"></a><span data-ttu-id="c21be-102">Примечание о подключении Lync-Skype в Lync Server 2013 для клиентов Lync Online</span><span class="sxs-lookup"><span data-stu-id="c21be-102">Note about Lync-Skype connectivity in Lync Server 2013 for Lync Online customers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c21be-103">_**Последнее изменение темы:** 2013-09-23_</span><span class="sxs-lookup"><span data-stu-id="c21be-103">_**Topic Last Modified:** 2013-09-23_</span></span>

<span data-ttu-id="c21be-104">Этот документ был написан, чтобы помочь локальным администраторам Lync Server настроить подключение Lync — Skype.</span><span class="sxs-lookup"><span data-stu-id="c21be-104">This document was written to help Lync Server on-premise administrators set up Lync-Skype connectivity.</span></span><span data-ttu-id="c21be-105">Lync Online Connectivity — это также функция Lync Online, которая входит в состав Office 365.</span><span class="sxs-lookup"><span data-stu-id="c21be-105">  Lync-Skype connectivity is also a feature of Lync Online, which is part of Office 365.</span></span> <span data-ttu-id="c21be-106">Вы можете включить функцию подключения Lync — Skype из центра администрирования Lync в центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c21be-106">You can enable the Lync-Skype connectivity feature from the Lync Administration Center within the Microsoft 365 admin center.</span></span>

<span data-ttu-id="c21be-107">Для Office 365 среднего бизнеса, Office 365 корпоративный, Office 365 для образовательных учреждений и Office 365 для государственных учреждений: 365 войдите в центр администрирования Lync и перейдите в центр **администрирования Lync**.</span><span class="sxs-lookup"><span data-stu-id="c21be-107">For Office 365 Midsize Business, Office 365 Enterprise, Office 365 Education, and Office 365 for Government: Sign in to the Microsoft 365 admin center and navigate to the **Lync Administration Center**.</span></span> <span data-ttu-id="c21be-108">Перейдите к разделу **Внешние коммуникации**.</span><span class="sxs-lookup"><span data-stu-id="c21be-108">Go to **External Communications**.</span></span> <span data-ttu-id="c21be-109">В разделе **поставщики общедоступных служб обмена мгновенными сообщениями**нажмите кнопку **включить**.</span><span class="sxs-lookup"><span data-stu-id="c21be-109">Under **Public IM Service Providers**, click **Enable**.</span></span> <span data-ttu-id="c21be-110">Если вы хотите контролировать доступ отдельных пользователей к Lync — Skype, это можно сделать, изменив параметры внешних коммуникаций для отдельных пользователей.</span><span class="sxs-lookup"><span data-stu-id="c21be-110">If you want to control individual user access to Lync-Skype Connectivity, you can do so by editing individual users’ External Communications settings.</span></span>

<span data-ttu-id="c21be-111">Для Office 365 Small Business Premium: Войдите в систему и перейдите к разделу \*\* \> Настройка \> службы администрирования обмен мгновенными сообщениями, собрания и конференции\*\*.</span><span class="sxs-lookup"><span data-stu-id="c21be-111">For Office 365 Small Business Premium: Sign in, and go to **Admin \> Service Settings \> Instant messaging, meetings and conferencing**.</span></span> <span data-ttu-id="c21be-112">Включите внешние коммуникации.</span><span class="sxs-lookup"><span data-stu-id="c21be-112">Turn on External communications.</span></span> <span data-ttu-id="c21be-113">Внешний коммутатор связи включает в себя связь Lync и Skype с другими организациями, использующими Lync.</span><span class="sxs-lookup"><span data-stu-id="c21be-113">The External communications switch turns on both Lync-Skype connectivity and communications with other organizations that use Lync.</span></span> <span data-ttu-id="c21be-114">В зависимости от того, когда вы начали использовать Lync Online, внешний коммутатор связи в состоянии "вкл." может первоначально указывать только на то, что активируется связь с другими организациями Lync.</span><span class="sxs-lookup"><span data-stu-id="c21be-114">Depending on when you started using Lync Online, the External communications switch in an "on" state may initially indicate only that communications with other Lync organizations is activated.</span></span> <span data-ttu-id="c21be-115">Чтобы включить подключение Lync — Skype, просто переключите его и снова включите снова.</span><span class="sxs-lookup"><span data-stu-id="c21be-115">To turn on Lync-Skype Connectivity, simply toggle the switch off and then back on again.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

