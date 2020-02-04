---
title: 'Lync Server 2013: параметры согласования для федеративных XMPP-партнеров'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Negotiation settings for XMPP federated partners
ms:assetid: ef773942-ef92-4f71-85a1-738dfebdfa00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552456(v=OCS.15)
ms:contentKeyID: 48679567
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 995ee34d0a2dcf28ca6aa4f8158d0e08d1533191
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765940"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="negotiation-settings-for-xmpp-federated-partners-in-lync-server-2013"></a><span data-ttu-id="a504e-102">Параметры согласования для федеративных XMPP-партнеров в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a504e-102">Negotiation settings for XMPP federated partners in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a504e-103">_**Тема последнего изменения:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="a504e-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="a504e-104">Параметры типов согласования в конфигурации КСМПП партнера имеют широкий спектр возможных комбинаций.</span><span class="sxs-lookup"><span data-stu-id="a504e-104">The settings for the negotiation types in the configuration of an XMPP Partner have a wide variety of possible combinations.</span></span> <span data-ttu-id="a504e-105">Не все из этих сочетаний являются допустимыми.</span><span class="sxs-lookup"><span data-stu-id="a504e-105">Not all of these combinations are valid.</span></span> <span data-ttu-id="a504e-106">В таблице, подробно описанной в этом разделе, определяются допустимые и недопустимые параметры.</span><span class="sxs-lookup"><span data-stu-id="a504e-106">The table detailed in this topic will define the valid and not valid settings.</span></span> <span data-ttu-id="a504e-107">Общие конфигурации представлены в первой таблице, во второй — на всех возможных комбинациях.</span><span class="sxs-lookup"><span data-stu-id="a504e-107">Common configurations are presented in the first table, the second table detailing all possible combinations.</span></span> <span data-ttu-id="a504e-108">Обратите внимание на то, что вы не можете использовать *простую проверку подлинности и уровень безопасности* (SASL), **если** также не доступен TLS- *Безопасность* .</span><span class="sxs-lookup"><span data-stu-id="a504e-108">Note that you cannot have *Simple Authentication and Security Layer* (SASL) **unless** *Transport Layer Security* (TLS) is also available.</span></span> <span data-ttu-id="a504e-109">SASL отправляется в незашифрованном (читаемом) формате, и его не следует передавать, если только они не защищены другим способом, например TLS.</span><span class="sxs-lookup"><span data-stu-id="a504e-109">SASL is sent in an unencrypted (readable) format and should never be transmitted unless protected by another means, such as TLS.</span></span>

### <a name="common-xmpp-federation-negotiation-methods"></a><span data-ttu-id="a504e-110">Распространенные методы согласования КСМПП Федерации</span><span class="sxs-lookup"><span data-stu-id="a504e-110">Common XMPP Federation Negotiation Methods</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a504e-111">Безопасность уровня транспорта (TLS)</span><span class="sxs-lookup"><span data-stu-id="a504e-111">Transport Layer Security (TLS)</span></span></th>
<th><span data-ttu-id="a504e-112">Простая проверка подлинности и уровень безопасности (SASL)</span><span class="sxs-lookup"><span data-stu-id="a504e-112">Simple Authentication and Security Layer (SASL)</span></span></th>
<th><span data-ttu-id="a504e-113">Проверка подлинности диалбакк</span><span class="sxs-lookup"><span data-stu-id="a504e-113">Dialback Authentication</span></span></th>
<th><span data-ttu-id="a504e-114">Ожидаемый метод проверки подлинности (-ов)</span><span class="sxs-lookup"><span data-stu-id="a504e-114">Expected Authentication Method(s)</span></span></th>
<th><span data-ttu-id="a504e-115">Notes</span><span class="sxs-lookup"><span data-stu-id="a504e-115">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a504e-116"> Обязательно</span><span class="sxs-lookup"><span data-stu-id="a504e-116">Required</span></span></p></td>
<td><p><span data-ttu-id="a504e-117">Обязательно</span><span class="sxs-lookup"><span data-stu-id="a504e-117">Required</span></span></p></td>
<td><p><span data-ttu-id="a504e-118">False</span><span class="sxs-lookup"><span data-stu-id="a504e-118">False</span></span></p></td>
<td><p><span data-ttu-id="a504e-119">SASL по протоколу TLS</span><span class="sxs-lookup"><span data-stu-id="a504e-119">SASL over TLS</span></span></p></td>
<td><p><span data-ttu-id="a504e-120">TLS и SASL должны обеспечивать безопасность потока сообщений SASL.</span><span class="sxs-lookup"><span data-stu-id="a504e-120">TLS and SASL required helps to ensure that the SASL message stream is secure.</span></span> <span data-ttu-id="a504e-121">Диалбакк недоступен и не может использоваться для резервного метода в том случае, если для федеративного партнера КСМПП не задано обязательное или необязательное значение TLS.</span><span class="sxs-lookup"><span data-stu-id="a504e-121">Dialback is not available and cannot be used for a fallback method if the XMPP federated partner has not set TLS to required or optional.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a504e-122">Обязательный</span><span class="sxs-lookup"><span data-stu-id="a504e-122">Required</span></span></p></td>
<td><p><span data-ttu-id="a504e-123">Необязательно </span><span class="sxs-lookup"><span data-stu-id="a504e-123">Optional</span></span></p></td>
<td><p><span data-ttu-id="a504e-124">Верно</span><span class="sxs-lookup"><span data-stu-id="a504e-124">True</span></span></p></td>
<td><p><span data-ttu-id="a504e-125">SASL over TLS, TLS Диалбакк, TCP Диалбакк</span><span class="sxs-lookup"><span data-stu-id="a504e-125">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="a504e-126">Если для федеративного партнера КСМПП задано значение SASL для необязательного или требуемого SASL, используется TLS.</span><span class="sxs-lookup"><span data-stu-id="a504e-126">By requiring TLS, if the XMPP federated partner has set SASL to optional or required SASL is used.</span></span> <span data-ttu-id="a504e-127">Если SASL недоступен, будет использоваться Диалбакк по TLS.</span><span class="sxs-lookup"><span data-stu-id="a504e-127">If SASL is not available, Dialback over TLS will be used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a504e-128">Необязательно </span><span class="sxs-lookup"><span data-stu-id="a504e-128">Optional</span></span></p></td>
<td><p><span data-ttu-id="a504e-129">Необязательно</span><span class="sxs-lookup"><span data-stu-id="a504e-129">Optional</span></span></p></td>
<td><p><span data-ttu-id="a504e-130">Верно</span><span class="sxs-lookup"><span data-stu-id="a504e-130">True</span></span></p></td>
<td><p><span data-ttu-id="a504e-131">SASL over TLS, TLS Диалбакк, TCP Диалбакк</span><span class="sxs-lookup"><span data-stu-id="a504e-131">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="a504e-132">Несмотря на то, что предлагаемые методы согласования очень гибки, эти параметры основываются на параметрах партнера КСМПП Федерации.</span><span class="sxs-lookup"><span data-stu-id="a504e-132">While very flexible in the negotiation methods offered, these settings rely on the XMPP federation partner’s settings.</span></span> <span data-ttu-id="a504e-133">Если у партнера есть TLS, необязательный или обязательный, но SASL не поддерживается, TLS Диалбакк будет доступен.</span><span class="sxs-lookup"><span data-stu-id="a504e-133">If the partner has TLS optional or required but SASL is not supported, TLS Dialback will be available.</span></span> <span data-ttu-id="a504e-134">Если у партнера есть TLS и SASL, для которых установлен необязательный или обязательный вариант, используется оптимальный выбор TLS более SASL.</span><span class="sxs-lookup"><span data-stu-id="a504e-134">If the partner has TLS and SASL set to optional or required, the optimal selection of TLS over SASL is used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a504e-135">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="a504e-135">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="a504e-136">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="a504e-136">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="a504e-137">Верно</span><span class="sxs-lookup"><span data-stu-id="a504e-137">True</span></span></p></td>
<td><p><span data-ttu-id="a504e-138">TCP Диалбакк</span><span class="sxs-lookup"><span data-stu-id="a504e-138">TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="a504e-139">Во многих случаях TCP Диалбакк является единственным возможным решением.</span><span class="sxs-lookup"><span data-stu-id="a504e-139">In many cases, TCP Dialback is the only possible solution.</span></span> <span data-ttu-id="a504e-140">Менее предпочтительнее, чем другие параметры, она обеспечивает некоторый уровень доверия.</span><span class="sxs-lookup"><span data-stu-id="a504e-140">Less desirable than other options, it does provide some level of trust.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="xmpp-federation-negotiation-methods-matrix---complete"></a><span data-ttu-id="a504e-141">Матрица методов согласования КСМПП Федерации — завершено</span><span class="sxs-lookup"><span data-stu-id="a504e-141">XMPP Federation Negotiation Methods Matrix - Complete</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a504e-142">Безопасность уровня транспорта (TLS)</span><span class="sxs-lookup"><span data-stu-id="a504e-142">Transport Layer Security (TLS)</span></span></th>
<th><span data-ttu-id="a504e-143">Простая проверка подлинности и уровень безопасности (SASL)</span><span class="sxs-lookup"><span data-stu-id="a504e-143">Simple Authentication and Security Layer (SASL)</span></span></th>
<th><span data-ttu-id="a504e-144">Проверка подлинности диалбакк</span><span class="sxs-lookup"><span data-stu-id="a504e-144">Dialback Authentication</span></span></th>
<th><span data-ttu-id="a504e-145">Ожидаемый метод проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="a504e-145">Expected Authentication Method</span></span></th>
<th><span data-ttu-id="a504e-146">Заметки, предупреждение или ошибка для недействительной конфигурации</span><span class="sxs-lookup"><span data-stu-id="a504e-146">Notes, Warning or Error for Not Valid Configuration</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a504e-147"> Обязательно</span><span class="sxs-lookup"><span data-stu-id="a504e-147">Required</span></span></p></td>
<td><p><span data-ttu-id="a504e-148">Обязательно</span><span class="sxs-lookup"><span data-stu-id="a504e-148">Required</span></span></p></td>
<td><p><span data-ttu-id="a504e-149">Верно</span><span class="sxs-lookup"><span data-stu-id="a504e-149">True</span></span></p></td>
<td><p><span data-ttu-id="a504e-150">SASL по протоколу TLS</span><span class="sxs-lookup"><span data-stu-id="a504e-150">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="a504e-151">Диалбакк не будет работать, если требуются оба SASL и TLS.</span><span class="sxs-lookup"><span data-stu-id="a504e-151">Dialback will not operate if both SASL and TLS are required.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a504e-152"> Обязательно</span><span class="sxs-lookup"><span data-stu-id="a504e-152">Required</span></span></p></td>
<td><p><span data-ttu-id="a504e-153">Обязательно</span><span class="sxs-lookup"><span data-stu-id="a504e-153">Required</span></span></p></td>
<td><p><span data-ttu-id="a504e-154">False</span><span class="sxs-lookup"><span data-stu-id="a504e-154">False</span></span></p></td>
<td><p><span data-ttu-id="a504e-155">SASL по протоколу TLS</span><span class="sxs-lookup"><span data-stu-id="a504e-155">SASL over TLS</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a504e-156">Необязательно </span><span class="sxs-lookup"><span data-stu-id="a504e-156">Optional</span></span></p></td>
<td><p><span data-ttu-id="a504e-157">Обязательный</span><span class="sxs-lookup"><span data-stu-id="a504e-157">Required</span></span></p></td>
<td><p><span data-ttu-id="a504e-158">Верно</span><span class="sxs-lookup"><span data-stu-id="a504e-158">True</span></span></p></td>
<td><p><span data-ttu-id="a504e-159">SASL over TLS, TLS Диалбакк, TCP Диалбакк</span><span class="sxs-lookup"><span data-stu-id="a504e-159">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="a504e-160">Для SASL требуется TLS.</span><span class="sxs-lookup"><span data-stu-id="a504e-160">SASL requires TLS.</span></span> <span data-ttu-id="a504e-161">Если вы разрешаете использовать TLS, может возникнуть сбой согласования сеанса.</span><span class="sxs-lookup"><span data-stu-id="a504e-161">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a504e-162">Необязательно </span><span class="sxs-lookup"><span data-stu-id="a504e-162">Optional</span></span></p></td>
<td><p><span data-ttu-id="a504e-163">Обязательный</span><span class="sxs-lookup"><span data-stu-id="a504e-163">Required</span></span></p></td>
<td><p><span data-ttu-id="a504e-164">False</span><span class="sxs-lookup"><span data-stu-id="a504e-164">False</span></span></p></td>
<td><p><span data-ttu-id="a504e-165">SASL по протоколу TLS</span><span class="sxs-lookup"><span data-stu-id="a504e-165">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="a504e-166">Для SASL требуется TLS.</span><span class="sxs-lookup"><span data-stu-id="a504e-166">SASL requires TLS.</span></span> <span data-ttu-id="a504e-167">Если вы разрешаете использовать TLS, может возникнуть сбой согласования сеанса.</span><span class="sxs-lookup"><span data-stu-id="a504e-167">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a504e-168">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="a504e-168">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="a504e-169">Обязательный</span><span class="sxs-lookup"><span data-stu-id="a504e-169">Required</span></span></p></td>
<td><p><span data-ttu-id="a504e-170">Верно</span><span class="sxs-lookup"><span data-stu-id="a504e-170">True</span></span></p></td>
<td><p><span data-ttu-id="a504e-171">TCP Диалбакк</span><span class="sxs-lookup"><span data-stu-id="a504e-171">TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="a504e-172">Для SASL требуется TLS.</span><span class="sxs-lookup"><span data-stu-id="a504e-172">SASL requires TLS.</span></span> <span data-ttu-id="a504e-173">Если вы разрешаете использовать TLS, может возникнуть сбой согласования сеанса.</span><span class="sxs-lookup"><span data-stu-id="a504e-173">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a504e-174">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="a504e-174">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="a504e-175">Обязательный</span><span class="sxs-lookup"><span data-stu-id="a504e-175">Required</span></span></p></td>
<td><p><span data-ttu-id="a504e-176">False</span><span class="sxs-lookup"><span data-stu-id="a504e-176">False</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="a504e-177">Недействительная конфигурация</span><span class="sxs-lookup"><span data-stu-id="a504e-177">Not Valid Configuration</span></span>


</div></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="a504e-178">Так как для SASL требуется протокол TLS, а протокол TLS недоступен, SASL/TLS выполнить не удастся.</span><span class="sxs-lookup"><span data-stu-id="a504e-178">Because SASL requires TLS, and TLS is not available, SASL/TLS cannot succeed.</span></span> <span data-ttu-id="a504e-179">Для TCP Диалбакк задано значение false, и его нельзя использовать.</span><span class="sxs-lookup"><span data-stu-id="a504e-179">TCP Dialback is set to false, and cannot be used.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a504e-180">Обязательный</span><span class="sxs-lookup"><span data-stu-id="a504e-180">Required</span></span></p></td>
<td><p><span data-ttu-id="a504e-181">Необязательно </span><span class="sxs-lookup"><span data-stu-id="a504e-181">Optional</span></span></p></td>
<td><p><span data-ttu-id="a504e-182">Верно</span><span class="sxs-lookup"><span data-stu-id="a504e-182">True</span></span></p></td>
<td><p><span data-ttu-id="a504e-183">SASL over TLS, Диалбакк TLS</span><span class="sxs-lookup"><span data-stu-id="a504e-183">SASL over TLS, TLS Dialback</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a504e-184">Обязательный</span><span class="sxs-lookup"><span data-stu-id="a504e-184">Required</span></span></p></td>
<td><p><span data-ttu-id="a504e-185">Необязательно </span><span class="sxs-lookup"><span data-stu-id="a504e-185">Optional</span></span></p></td>
<td><p><span data-ttu-id="a504e-186">False</span><span class="sxs-lookup"><span data-stu-id="a504e-186">False</span></span></p></td>
<td><p><span data-ttu-id="a504e-187">SASL по протоколу TLS</span><span class="sxs-lookup"><span data-stu-id="a504e-187">SASL over TLS</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a504e-188">Необязательно </span><span class="sxs-lookup"><span data-stu-id="a504e-188">Optional</span></span></p></td>
<td><p><span data-ttu-id="a504e-189">Необязательно</span><span class="sxs-lookup"><span data-stu-id="a504e-189">Optional</span></span></p></td>
<td><p><span data-ttu-id="a504e-190">Верно</span><span class="sxs-lookup"><span data-stu-id="a504e-190">True</span></span></p></td>
<td><p><span data-ttu-id="a504e-191">SASL over TLS, TLS Диалбакк, TCP Диалбакк</span><span class="sxs-lookup"><span data-stu-id="a504e-191">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="a504e-192">Для SASL требуется TLS.</span><span class="sxs-lookup"><span data-stu-id="a504e-192">SASL requires TLS.</span></span> <span data-ttu-id="a504e-193">Если вы разрешаете использовать TLS, может возникнуть сбой согласования сеанса.</span><span class="sxs-lookup"><span data-stu-id="a504e-193">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a504e-194">Необязательно </span><span class="sxs-lookup"><span data-stu-id="a504e-194">Optional</span></span></p></td>
<td><p><span data-ttu-id="a504e-195">Необязательно</span><span class="sxs-lookup"><span data-stu-id="a504e-195">Optional</span></span></p></td>
<td><p><span data-ttu-id="a504e-196">False</span><span class="sxs-lookup"><span data-stu-id="a504e-196">False</span></span></p></td>
<td><p><span data-ttu-id="a504e-197">SASL по протоколу TLS</span><span class="sxs-lookup"><span data-stu-id="a504e-197">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="a504e-198">Для SASL требуется TLS.</span><span class="sxs-lookup"><span data-stu-id="a504e-198">SASL requires TLS.</span></span> <span data-ttu-id="a504e-199">Если вы разрешаете использовать TLS, может возникнуть сбой согласования сеанса.</span><span class="sxs-lookup"><span data-stu-id="a504e-199">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a504e-200">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="a504e-200">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="a504e-201">Необязательно </span><span class="sxs-lookup"><span data-stu-id="a504e-201">Optional</span></span></p></td>
<td><p><span data-ttu-id="a504e-202">Верно</span><span class="sxs-lookup"><span data-stu-id="a504e-202">True</span></span></p></td>
<td><p><span data-ttu-id="a504e-203">TCP Диалбакк</span><span class="sxs-lookup"><span data-stu-id="a504e-203">TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="a504e-204">Для SASL требуется TLS.</span><span class="sxs-lookup"><span data-stu-id="a504e-204">SASL requires TLS.</span></span> <span data-ttu-id="a504e-205">Если вы разрешаете использовать TLS, может возникнуть сбой согласования сеанса.</span><span class="sxs-lookup"><span data-stu-id="a504e-205">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a504e-206">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="a504e-206">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="a504e-207">Необязательно </span><span class="sxs-lookup"><span data-stu-id="a504e-207">Optional</span></span></p></td>
<td><p><span data-ttu-id="a504e-208">False</span><span class="sxs-lookup"><span data-stu-id="a504e-208">False</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="a504e-209">Недействительная конфигурация</span><span class="sxs-lookup"><span data-stu-id="a504e-209">Not Valid Configuration</span></span>


</div></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="a504e-210">Для SASL требуется TLS.</span><span class="sxs-lookup"><span data-stu-id="a504e-210">SASL requires TLS.</span></span> <span data-ttu-id="a504e-211">Если вы разрешаете использовать TLS, может возникнуть сбой согласования сеанса.</span><span class="sxs-lookup"><span data-stu-id="a504e-211">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a504e-212">Обязательный</span><span class="sxs-lookup"><span data-stu-id="a504e-212">Required</span></span></p></td>
<td><p><span data-ttu-id="a504e-213">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="a504e-213">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="a504e-214">Верно</span><span class="sxs-lookup"><span data-stu-id="a504e-214">True</span></span></p></td>
<td><p><span data-ttu-id="a504e-215">TLS Диалбакк</span><span class="sxs-lookup"><span data-stu-id="a504e-215">TLS Dialback</span></span></p></td>
<td><p><span data-ttu-id="a504e-216">Настройка позволяет TLS Диалбакк.</span><span class="sxs-lookup"><span data-stu-id="a504e-216">Configuration allows for TLS Dialback.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a504e-217">Обязательный</span><span class="sxs-lookup"><span data-stu-id="a504e-217">Required</span></span></p></td>
<td><p><span data-ttu-id="a504e-218">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="a504e-218">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="a504e-219">False</span><span class="sxs-lookup"><span data-stu-id="a504e-219">False</span></span></p></td>
<td><p><span data-ttu-id="a504e-220">Недействительная конфигурация</span><span class="sxs-lookup"><span data-stu-id="a504e-220">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="a504e-221">Необходимо включить SASL или Диалбакк.</span><span class="sxs-lookup"><span data-stu-id="a504e-221">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a504e-222">Необязательно </span><span class="sxs-lookup"><span data-stu-id="a504e-222">Optional</span></span></p></td>
<td><p><span data-ttu-id="a504e-223">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="a504e-223">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="a504e-224">Верно</span><span class="sxs-lookup"><span data-stu-id="a504e-224">True</span></span></p></td>
<td><p><span data-ttu-id="a504e-225">TLS Диалбакк, TCP Диалбакк</span><span class="sxs-lookup"><span data-stu-id="a504e-225">TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="a504e-226">На основе вариантов согласования для другой конечной точки, TCP или TLS Диалбакк будут приняты.</span><span class="sxs-lookup"><span data-stu-id="a504e-226">Based on negotiation choices of the other end point, TCP or TLS Dialback will be accepted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a504e-227">Необязательно </span><span class="sxs-lookup"><span data-stu-id="a504e-227">Optional</span></span></p></td>
<td><p><span data-ttu-id="a504e-228">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="a504e-228">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="a504e-229">False</span><span class="sxs-lookup"><span data-stu-id="a504e-229">False</span></span></p></td>
<td><p><span data-ttu-id="a504e-230">Недействительная конфигурация</span><span class="sxs-lookup"><span data-stu-id="a504e-230">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="a504e-231">Необходимо включить SASL или Диалбакк.</span><span class="sxs-lookup"><span data-stu-id="a504e-231">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a504e-232">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="a504e-232">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="a504e-233">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="a504e-233">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="a504e-234">Верно</span><span class="sxs-lookup"><span data-stu-id="a504e-234">True</span></span></p></td>
<td><p><span data-ttu-id="a504e-235">TCP Диалбакк</span><span class="sxs-lookup"><span data-stu-id="a504e-235">TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="a504e-236">Протокол TCP Диалбакк является единственным доступным способом согласования</span><span class="sxs-lookup"><span data-stu-id="a504e-236">TCP Dialback is the only negotiation method available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a504e-237">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="a504e-237">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="a504e-238">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="a504e-238">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="a504e-239">False</span><span class="sxs-lookup"><span data-stu-id="a504e-239">False</span></span></p></td>
<td><p><span data-ttu-id="a504e-240">Недействительная конфигурация</span><span class="sxs-lookup"><span data-stu-id="a504e-240">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="a504e-241">Необходимо включить SASL или Диалбакк.</span><span class="sxs-lookup"><span data-stu-id="a504e-241">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

