---
title: 'Lync Server 2013: Настройка расширенных 9-1-1'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Enhanced 9-1-1
ms:assetid: 5967de00-c8b9-4923-86da-6ad3369a4cad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398390(v=OCS.15)
ms:contentKeyID: 48184205
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9851bdb85f0bbd91d0b58897656186c739ecbf8f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028570"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-enhanced-9-1-1-in-lync-server-2013"></a><span data-ttu-id="ad0dd-102">Настройка расширенного 9-1-1 в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ad0dd-102">Configure Enhanced 9-1-1 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ad0dd-103">_**Последнее изменение темы:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="ad0dd-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="ad0dd-p101">Enhanced 9-1-1 (E9-1-1) — это функция уведомления об экстренных случаях, которая связывает номер телефона вызывающего абонента с городским или почтовым адресом. Используя эти сведения, PSAP (Public Safety Answering Point) может незамедлительно направить службы экстренной помощи абоненту, находящемуся в бедственном положении.</span><span class="sxs-lookup"><span data-stu-id="ad0dd-p101">Enhanced 9-1-1 (E9-1-1) is an emergency notification feature that associates the calling party’s telephone number with a civic or a street address. Using this information, the Public Safety Answering Point (PSAP) can immediately dispatch emergency services to the caller in distress.</span></span>

<span data-ttu-id="ad0dd-106">Чтобы обеспечить поддержку E9-1-1, Lync Server 2013 должен иметь возможность правильно связать расположение с клиентом и убедиться в том, что эти сведения используются для маршрутизации экстренного вызова в ближайшее PSAP.</span><span class="sxs-lookup"><span data-stu-id="ad0dd-106">To support E9-1-1, Lync Server 2013 must be able to correctly associate a location with a client and to make sure that this information is used to route the emergency call to the nearest PSAP.</span></span>

<span data-ttu-id="ad0dd-107">Сведения о планировании развертывания E9-1-1 можно найти в статье [планирование экстренных служб (E9-1-1) в Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md).</span><span class="sxs-lookup"><span data-stu-id="ad0dd-107">For details about planning for an E9-1-1 deployment, see [Planning for emergency services (E9-1-1) in Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ad0dd-108">Lync Server 2013 поддерживает только E9 – 1 – 1 в США.</span><span class="sxs-lookup"><span data-stu-id="ad0dd-108">Lync Server 2013 only supports E9-1-1 within the United States.</span></span> <span data-ttu-id="ad0dd-109">Чтобы развернуть E9-1-1, необходимо настроить подключение SIP к квалифицированному поставщику услуг E9-1-1 или развернуть шлюз с идентификационным номером для экстренной службы (ELIN) на основе поставщика услуг E9-1-1 на основе общедоступного коммутируемого телефона (PSTN).</span><span class="sxs-lookup"><span data-stu-id="ad0dd-109">To deploy E9-1-1, you need to configure a SIP connection to a qualified E9-1-1 service provider, or deploy an emergency location identification number (ELIN) gateway to a public switched telephone (PSTN)-based E9-1-1 service provider.</span></span> <span data-ttu-id="ad0dd-110">Дополнительные сведения: <A href="lync-server-2013-enhanced-9-1-1-e9-1-1-and-mediation-server.md">расширенный 9-1-1 (E9-1-1) и сервер-посредник в Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="ad0dd-110">For details, see <A href="lync-server-2013-enhanced-9-1-1-e9-1-1-and-mediation-server.md">Enhanced 9-1-1 (E9-1-1) and Mediation Server in Lync Server 2013</A>.</span></span> <span data-ttu-id="ad0dd-111">Дополнительные сведения о настройке магистральных соединений приведены <A href="lync-server-2013-configure-a-trunk-with-media-bypass.md">в статье Настройка магистрали с обходом сервера мультимедиа в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="ad0dd-111">For details about configuring trunk connections, see <A href="lync-server-2013-configure-a-trunk-with-media-bypass.md">Configure a trunk with media bypass in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ad0dd-112">Содержание</span><span class="sxs-lookup"><span data-stu-id="ad0dd-112">In This Section</span></span>

  - [<span data-ttu-id="ad0dd-113">Настройка маршрута голосовой связи E9 – 1 – 1 в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ad0dd-113">Configure an E9-1-1 voice route in Lync Server 2013</span></span>](lync-server-2013-configure-an-e9-1-1-voice-route.md)

  - [<span data-ttu-id="ad0dd-114">Создание политик расположения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ad0dd-114">Create location policies in Lync Server 2013</span></span>](lync-server-2013-create-location-policies.md)

  - [<span data-ttu-id="ad0dd-115">Настройка сведений о сайте для E9-1-1 в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ad0dd-115">Configure site information for E9-1-1 in Lync Server 2013</span></span>](lync-server-2013-configure-site-information-for-e9-1-1.md)

  - [<span data-ttu-id="ad0dd-116">Настройка базы данных местоположений в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ad0dd-116">Configure the location database in Lync Server 2013</span></span>](lync-server-2013-configure-the-location-database.md)

  - [<span data-ttu-id="ad0dd-117">Настройка расширенных функций E9 – 1 – 1 в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ad0dd-117">Configure advanced E9-1-1 features in Lync Server 2013</span></span>](lync-server-2013-configure-advanced-e9-1-1-features.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

