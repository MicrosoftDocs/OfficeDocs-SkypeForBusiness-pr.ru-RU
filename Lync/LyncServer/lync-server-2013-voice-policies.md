---
title: 'Lync Server 2013: политики голосовой связи'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Voice policies
ms:assetid: b7433c62-9d8c-48af-89a0-19f0d34806ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412891(v=OCS.15)
ms:contentKeyID: 48185223
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 986350a766716cc8a1fc35a734933f30b25a70ec
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211095"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="voice-policies-in-lync-server-2013"></a><span data-ttu-id="892db-102">Политики голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="892db-102">Voice policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="892db-103">_**Последнее изменение темы:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="892db-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="892db-104">*Политики голосовой связи* Lync Server определяют указанные ниже сведения для каждого пользователя, сайта или организации, которым назначена политика.</span><span class="sxs-lookup"><span data-stu-id="892db-104">Lync Server *voice policies* define the following for each user, site, or organization that is assigned the policy:</span></span>

  - <span data-ttu-id="892db-105">Набор функций звонков, которые могут быть включены или отключены для определения функциональных возможностей корпоративной голосовой связи, доступных пользователям.</span><span class="sxs-lookup"><span data-stu-id="892db-105">A set of calling features that can be enabled or disabled to determine the Enterprise Voice functionality available to users.</span></span>

  - <span data-ttu-id="892db-106">набор режимов работы с ТСОП, который определяет разрешенные типы звонков.</span><span class="sxs-lookup"><span data-stu-id="892db-106">A set of public switched telephone network (PSTN) usage records that define what types of calls are authorized.</span></span>

<div>

## <a name="planning-for-voice-policies"></a><span data-ttu-id="892db-107">Планирование политик голосовых служб</span><span class="sxs-lookup"><span data-stu-id="892db-107">Planning for Voice Policies</span></span>

<span data-ttu-id="892db-108">Приведенные ниже инструкции помогут спланировать политики голосовой связи, которые понадобятся для развертывания корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="892db-108">The following steps will help you plan the voice policies that you will need for your Enterprise Voice deployment:</span></span>

  - <span data-ttu-id="892db-109">Определите, как будет настраиваться Глобальная политика голосовой связи (политика голосовой связи по умолчанию, установленная вместе с продуктом).</span><span class="sxs-lookup"><span data-stu-id="892db-109">Determine how you will configure your global voice policy (the default voice policy that is installed with the product).</span></span> <span data-ttu-id="892db-110">Эта политика будет применяться ко всем пользователям корпоративной голосовой связи, которым не назначена политика на уровне сайта или на уровне пользователя.</span><span class="sxs-lookup"><span data-stu-id="892db-110">This policy will apply to all Enterprise Voice users who are not explicitly assigned a site-level or per-user policy.</span></span>

  - <span data-ttu-id="892db-111">определение требуемых политик голосовой связи на уровне сайта;</span><span class="sxs-lookup"><span data-stu-id="892db-111">Identify any site-level voice policies that you might need.</span></span>

  - <span data-ttu-id="892db-112">определение требуемых политик голосовой связи на уровне пользователя;</span><span class="sxs-lookup"><span data-stu-id="892db-112">Identify any per-user voice policies that you might need.</span></span>

  - <span data-ttu-id="892db-113">Определение функций звонков, которые будут включены для каждой политики голосовых служб.</span><span class="sxs-lookup"><span data-stu-id="892db-113">Decide which call features to enable for each voice policy.</span></span>

  - <span data-ttu-id="892db-114">Определение режимов работы с ТСОП, задаваемых для каждой политики голосовых служб.</span><span class="sxs-lookup"><span data-stu-id="892db-114">Determine what PSTN usage records to configure for each voice policy.</span></span>

<div>

## <a name="voice-policy-scope"></a><span data-ttu-id="892db-115">Область политики голосовых служб</span><span class="sxs-lookup"><span data-stu-id="892db-115">Voice Policy Scope</span></span>

<span data-ttu-id="892db-116">*Область политики голосовых служб* определяет иерархический уровень, на котором применяется политика.</span><span class="sxs-lookup"><span data-stu-id="892db-116">*Voice policy scope* determines the hierarchical level at which the policy can be applied.</span></span> <span data-ttu-id="892db-117">В Lync Server можно настроить политики голосовой связи со следующими уровнями областей (в порядке, определяемом наиболее общим).</span><span class="sxs-lookup"><span data-stu-id="892db-117">In Lync Server, you can configure voice policies with the following scope levels (listed from the most specific to the most general).</span></span>

  - <span data-ttu-id="892db-p103">**Политика голосовой связи на уровне пользователя** может быть назначена отдельным пользователям, группам или контактным объектам. Это политика самого низкого уровня. С помощью пользовательских политик голосовой связи можно включить функции для определенных пользователей или групп пользователей сайта. Например, вам может потребоваться отключить международную связь для некоторых сотрудников. При назначении политики голосовой связи контактный объект рассматривается как отдельный пользователь.</span><span class="sxs-lookup"><span data-stu-id="892db-p103">**User voice policy** can be assigned to individual users, groups, or contact objects. This is the lowest level policy. User voice policies can be deployed to enable features for certain users or groups at a site, but not for others in the same site. For example, you may want to disable long distance dialing for some employees. For the purpose of assigning a voice policy, a contact object is treated as an individual user.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="892db-123">Рекомендуется развернуть политику голосовой связи для пользователей корпоративной голосовой связи на сайте филиала, зарегистрированных в развертывании центрального сайта, или пользователей, зарегистрированных на устройстве для обеспечения связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="892db-123">We recommend that you deploy a user voice policy for branch site Enterprise Voice users who are registered with the central site deployment, or users who are registered on a Survivable Branch Appliance.</span></span>

    
    </div>

  - <span data-ttu-id="892db-p104">**Политика голосовой связи на уровне сайта** применяется ко всему сайту за исключением пользователей, групп или контактных объектов, которым назначена политика голосовой связи на уровне пользователя. Чтобы определить политику голосовой связи на уровне сайта, вам нужно указать сайт, к которому применяется политика. Если политика голосовой связи на уровне пользователя не назначена, то используется политика голосовой связи на уровне сайта.</span><span class="sxs-lookup"><span data-stu-id="892db-p104">**Site voice policy** applies to an entire site, except for any users, groups, or contact objects that are assigned a user voice policy. To define a site voice policy, you must specify the site to which the policy applies. If a user voice policy is not assigned, the site voice policy is used.</span></span>

  - <span data-ttu-id="892db-127">**Глобальная политика голосовой связи** — это политика голосовой связи по умолчанию, которая устанавливается вместе с продуктом.</span><span class="sxs-lookup"><span data-stu-id="892db-127">**Global voice policy** is the default voice policy that is installed with the product.</span></span> <span data-ttu-id="892db-128">Вы можете изменять глобальную политику голосовой связи в соответствии с потребностями организации, однако вы не можете переименовывать или удалять ее.</span><span class="sxs-lookup"><span data-stu-id="892db-128">You can edit the global voice policy to meet the specific needs of your organization, but you cannot rename or delete it.</span></span> <span data-ttu-id="892db-129">Эта политика голосовой связи применяется ко всем пользователям, группам и контактам корпоративной голосовой связи в развертывании, если не настроена и не назначена политика голосовой связи с более определенной областью.</span><span class="sxs-lookup"><span data-stu-id="892db-129">This voice policy applies to all Enterprise Voice users, groups, and contact objects in your deployment unless you configure and assign a voice policy with more specific scope.</span></span> <span data-ttu-id="892db-130">Если вы хотите полностью отключить эту политику, убедитесь в том, что для всех сайтов и пользователей назначены настраиваемые политики.</span><span class="sxs-lookup"><span data-stu-id="892db-130">If you want to disable this policy entirely, be sure that all sites and users have custom policies assigned to them.</span></span>

</div>

<div>

## <a name="call-features"></a><span data-ttu-id="892db-131">Функции звонков</span><span class="sxs-lookup"><span data-stu-id="892db-131">Call Features</span></span>

<span data-ttu-id="892db-132">Для каждой политики голосовых служб можно включать или отключать следующие функции звонков:</span><span class="sxs-lookup"><span data-stu-id="892db-132">You can enable or disable the following call features for each voice policy:</span></span>

  - <span data-ttu-id="892db-p106">**Переадресация звонков** позволяет пользователям переадресовывать звонки на другие телефоны и устройства клиента. Включена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="892db-p106">**Call forwarding** enables users to forward calls to other phones and client devices. Enabled by default.</span></span>

  - <span data-ttu-id="892db-p107">**Делегирование** позволяет пользователям указывать других пользователей, которые могут выполнять и принимать звонки от их имени. Включена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="892db-p107">**Delegation** enables users to specify other users to send and receive calls on their behalf. Enabled by default.</span></span>

  - <span data-ttu-id="892db-p108">**Перевод звонка** позволяет пользователям переводить звонки другим пользователям. Включена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="892db-p108">**Call transfer** enables users to transfer calls to other users. Enabled by default.</span></span>

  - <span data-ttu-id="892db-p109">**Парковка звонка** позволяет пользователям приостанавливать звонки и затем извлекать их на другом телефоне или клиенте. Отключена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="892db-p109">**Call park** enables users to park calls and then pick up the call from a different phone or client. Disabled by default.</span></span>

  - <span data-ttu-id="892db-p110">**Одновременные звонки** позволяет получать звонок на дополнительном телефоне (например, мобильном телефоне) или других устройствах конечной точки при получении входящего звонка. Включена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="892db-p110">**Simultaneous ringing** enables incoming calls to ring on an additional phone (for example, a mobile phone) or other endpoint devices. Enabled by default.</span></span>

  - <span data-ttu-id="892db-p111">**Групповой звонок** позволяет пользователям заданной группы отвечать на звонки других членов группы. Включена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="892db-p111">**Team call** enables users on a defined team to answer calls for other members of the team. Enabled by default.</span></span>

  - <span data-ttu-id="892db-p112">**Перенаправление ТСОП** позволяет перенаправлять в ТСОП звонки пользователей, которым назначена эта политика, другим пользователям организации, если глобальная сеть перегружена или недоступна. Включена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="892db-p112">**PSTN reroute** enables calls made by users who are assigned this policy to other enterprise users to be rerouted on the public switched telephone network (PSTN) if the WAN is congested or unavailable. Enabled by default.</span></span>

  - <span data-ttu-id="892db-p113">**Переопределение политики пропускной способности** позволяет администраторам переопределять политику контроля допуска звонков для определенных пользователей. Отключена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="892db-p113">**Bandwidth policy override** enables administrators to override call admission control policy decisions for a particular user. Disabled by default.</span></span>

  - <span data-ttu-id="892db-149">**Трассировка вредоносных вызовов** позволяет пользователям сообщать о вредоносных вызовах с помощью клиента Lync, а затем помечать такие вызовы в записях сведений о вызовах.</span><span class="sxs-lookup"><span data-stu-id="892db-149">**Malicious call tracing** enables users to report malicious calls by using the Lync client, and then flags such calls in the call detail records.</span></span> <span data-ttu-id="892db-150">Отключена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="892db-150">Disabled by default.</span></span>

  - <span data-ttu-id="892db-151">**Запрет на использование голосовой почты** предотвращает немедленное перенаправление звонков на голосовую почту мобильного телефона пользователя в течение заданного периода времени, если включена функция одновременных звонков и телефон отключен, разряжен или находится вне зоны действия сети.</span><span class="sxs-lookup"><span data-stu-id="892db-151">**Voicemail escape** prevents calls from being immediately routed to the user’s mobile phone voicemail system when simultaneous ringing is configured and the phone is turned off, out of battery, or out of range, and is based on a timer value.</span></span> <span data-ttu-id="892db-152">Этот параметр включает или отключает таймер и задает его значение.</span><span class="sxs-lookup"><span data-stu-id="892db-152">This setting enables and disables the timer and sets the value of the timer.</span></span> <span data-ttu-id="892db-153">Его можно настроить только с помощью командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="892db-153">It can be configured only by using the Lync Server Management Shell.</span></span> <span data-ttu-id="892db-154">По умолчанию параметр отключен.</span><span class="sxs-lookup"><span data-stu-id="892db-154">Disabled by default.</span></span>

  - <span data-ttu-id="892db-p116">**Режимы работы с ТСОП для переадресации звонков и одновременных звонков** позволяют администраторам указывать режим работы с ТСОП, используемый политикой голосовой связи для переадресации звонков и одновременных звонков, разрешать переадресацию звонков и одновременные звонки только внутренним пользователям Lync или указывать настраиваемые режимы работы с ТСОП, которые отличаются от режимов работы с ТСОП политики голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="892db-p116">**Call forwarding and simultaneous ringing PSTN usages** enables administrators to specify the same PSTN usage as the voice policy for call forwarding and simultaneous ringing, restrict call forwarding and simultaneous ringing to internal Lync users only, or specify a custom PSTN usage that is different from the voice policy’s PSTN usage. The default is to use the same PSTN usage as the voice policy for call forwarding and simultaneous ringing.</span></span>

</div>

<div>

## <a name="pstn-usage-records"></a><span data-ttu-id="892db-157">Режимы работы с ТСОП</span><span class="sxs-lookup"><span data-stu-id="892db-157">PSTN Usage Records</span></span>

<span data-ttu-id="892db-158">С каждой политикой голосовой связи должен быть связан как минимум один режим работы с ТСОП.</span><span class="sxs-lookup"><span data-stu-id="892db-158">Each voice policy should have one or more associated PSTN usage records.</span></span> <span data-ttu-id="892db-159">Режимы работы с ТСОП можно связать с политикой голосовой связи только для обеспечения одновременных звонков и переадресации звонков.</span><span class="sxs-lookup"><span data-stu-id="892db-159">PSTN usages can be associated with a voice policy for the purpose of simultaneous ringing and call forwarding only.</span></span> <span data-ttu-id="892db-160">Сведения о планировании записей использования PSTN приведены [в статье Использование PSTN в Lync Server 2013](lync-server-2013-pstn-usage-records.md).</span><span class="sxs-lookup"><span data-stu-id="892db-160">For details about planning PSTN usage records, see [PSTN usage records in Lync Server 2013](lync-server-2013-pstn-usage-records.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="892db-p118">Порядок указания режимов работы с ТСОП является критически важным, поскольку при сопоставлении пользователей с маршрутами функция исходящей маршрутизации сравнивает режимы работы с ТСОП сверху вниз. Если первый режим соответствует маршруту звонка, то будет использоваться этот маршрут. В противном случае функция исходящей маршрутизации выполняет поиск следующего режима работы с ТСОП до тех пор, пока соответствие не будет найдено. По сути последующие режимы работы с ТСОП представляют собой резервные копии, если первый режим в списке недоступен.</span><span class="sxs-lookup"><span data-stu-id="892db-p118">PSTN usage order is critical because in matching users to routes, the outbound routing functionality compares PSTN usages from top to bottom. If the first usage matches the call route, that route is used. If not, the outbound routing functionality looks at the next PSTN usage on the list and continues until a match is found. In effect, the subsequent PSTN usages provide backup if the first one on the list is unavailable.</span></span>



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

