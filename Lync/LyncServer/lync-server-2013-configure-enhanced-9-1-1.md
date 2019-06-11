---
title: 'Lync Server 2013: настройка службы Enhanced 9-1-1'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure Enhanced 9-1-1
ms:assetid: 5967de00-c8b9-4923-86da-6ad3369a4cad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398390(v=OCS.15)
ms:contentKeyID: 48184205
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0ef94e3de028f66684972fa6a3c95d4e63c35b5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841371"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-enhanced-9-1-1-in-lync-server-2013"></a><span data-ttu-id="29d65-102">Настройка службы Enhanced 9-1-1 в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="29d65-102">Configure Enhanced 9-1-1 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="29d65-103">_**Тема последнего изменения:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="29d65-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="29d65-p101">Enhanced 9-1-1 (E9-1-1) – это функция уведомления об экстренных случаях, которая связывает номер телефона вызывающего абонента с городским или почтовым адресом. Используя эти сведения, PSAP (Public Safety Answering Point) может незамедлительно направить службы экстренной помощи абоненту, находящемуся в бедственном положении.</span><span class="sxs-lookup"><span data-stu-id="29d65-p101">Enhanced 9-1-1 (E9-1-1) is an emergency notification feature that associates the calling party’s telephone number with a civic or a street address. Using this information, the Public Safety Answering Point (PSAP) can immediately dispatch emergency services to the caller in distress.</span></span>

<span data-ttu-id="29d65-106">Для поддержки E9-1-1 в Lync Server 2013 необходимо правильно связать расположение с клиентом и удостовериться, что эта информация используется для направления вызова экстренной помощи на ближайшее ПСАП.</span><span class="sxs-lookup"><span data-stu-id="29d65-106">To support E9-1-1, Lync Server 2013 must be able to correctly associate a location with a client and to make sure that this information is used to route the emergency call to the nearest PSAP.</span></span>

<span data-ttu-id="29d65-107">Для получения подробной информации о планировании развертывания E9-1-1, ознакомьтесь со статьей [Планирование служб экстренной помощи (E9-1-1) в Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md).</span><span class="sxs-lookup"><span data-stu-id="29d65-107">For details about planning for an E9-1-1 deployment, see [Planning for emergency services (E9-1-1) in Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="29d65-108">Lync Server 2013 поддерживает только E9-1-1 в США.</span><span class="sxs-lookup"><span data-stu-id="29d65-108">Lync Server 2013 only supports E9-1-1 within the United States.</span></span> <span data-ttu-id="29d65-109">Чтобы развернуть E9-1-1, вам нужно настроить подключение по протоколу SIP к квалифицированному поставщику услуг E9-1 или развернуть идентификационный номер места для экстренной помощи (Елин) для поставщика услуг с общедоступным коммутируемым телефонным подключением (Wi-Fi-1).</span><span class="sxs-lookup"><span data-stu-id="29d65-109">To deploy E9-1-1, you need to configure a SIP connection to a qualified E9-1-1 service provider, or deploy an emergency location identification number (ELIN) gateway to a public switched telephone (PSTN)-based E9-1-1 service provider.</span></span> <span data-ttu-id="29d65-110">Подробные сведения можно найти <A href="lync-server-2013-enhanced-9-1-1-e9-1-1-and-mediation-server.md">в разделе улучшенный 9-1-1 (E9-1-1) и сервер-посредник в Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="29d65-110">For details, see <A href="lync-server-2013-enhanced-9-1-1-e9-1-1-and-mediation-server.md">Enhanced 9-1-1 (E9-1-1) and Mediation Server in Lync Server 2013</A>.</span></span> <span data-ttu-id="29d65-111">Дополнительные сведения о настройке подключения к магистрали можно найти <A href="lync-server-2013-configure-a-trunk-with-media-bypass.md">в разделе Настройка магистрали с помощью мультимедийного обхода в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="29d65-111">For details about configuring trunk connections, see <A href="lync-server-2013-configure-a-trunk-with-media-bypass.md">Configure a trunk with media bypass in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="29d65-112">Содержание</span><span class="sxs-lookup"><span data-stu-id="29d65-112">In This Section</span></span>

  - [<span data-ttu-id="29d65-113">Настройка маршрута голосовой связи E9-1-1 в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="29d65-113">Configure an E9-1-1 voice route in Lync Server 2013</span></span>](lync-server-2013-configure-an-e9-1-1-voice-route.md)

  - [<span data-ttu-id="29d65-114">Создание политик местоположений в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="29d65-114">Create location policies in Lync Server 2013</span></span>](lync-server-2013-create-location-policies.md)

  - [<span data-ttu-id="29d65-115">Настройка сведений о сайте для E9-1-1 в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="29d65-115">Configure site information for E9-1-1 in Lync Server 2013</span></span>](lync-server-2013-configure-site-information-for-e9-1-1.md)

  - [<span data-ttu-id="29d65-116">Configure the location database in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="29d65-116">Configure the location database in Lync Server 2013</span></span>](lync-server-2013-configure-the-location-database.md)

  - [<span data-ttu-id="29d65-117">Настройка расширенных возможностей E9-1-1 в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="29d65-117">Configure advanced E9-1-1 features in Lync Server 2013</span></span>](lync-server-2013-configure-advanced-e9-1-1-features.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

