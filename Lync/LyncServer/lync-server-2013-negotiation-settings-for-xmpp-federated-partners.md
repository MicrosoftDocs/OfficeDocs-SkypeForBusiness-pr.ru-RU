---
title: 'Lync Server 2013: параметры согласования для федеративных XMPP-партнеров'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Negotiation settings for XMPP federated partners
ms:assetid: ef773942-ef92-4f71-85a1-738dfebdfa00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552456(v=OCS.15)
ms:contentKeyID: 48679567
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 02d72870e4060be6aa4ec428159af7ab19cb68b1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826712"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="negotiation-settings-for-xmpp-federated-partners-in-lync-server-2013"></a><span data-ttu-id="93aa4-102">Параметры согласования для федеративных XMPP-партнеров в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="93aa4-102">Negotiation settings for XMPP federated partners in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="93aa4-103">_**Тема последнего изменения:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="93aa4-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="93aa4-104">Параметры типов согласования в конфигурации КСМПП партнера имеют широкий спектр возможных комбинаций.</span><span class="sxs-lookup"><span data-stu-id="93aa4-104">The settings for the negotiation types in the configuration of an XMPP Partner have a wide variety of possible combinations.</span></span> <span data-ttu-id="93aa4-105">Не все из этих сочетаний являются допустимыми.</span><span class="sxs-lookup"><span data-stu-id="93aa4-105">Not all of these combinations are valid.</span></span> <span data-ttu-id="93aa4-106">В таблице, подробно описанной в этом разделе, определяются допустимые и недопустимые параметры.</span><span class="sxs-lookup"><span data-stu-id="93aa4-106">The table detailed in this topic will define the valid and not valid settings.</span></span> <span data-ttu-id="93aa4-107">Общие конфигурации представлены в первой таблице, во второй — на всех возможных комбинациях.</span><span class="sxs-lookup"><span data-stu-id="93aa4-107">Common configurations are presented in the first table, the second table detailing all possible combinations.</span></span> <span data-ttu-id="93aa4-108">Обратите внимание на то, что вы не можете использовать *простую проверку подлинности и уровень безопасности* (SASL), **если** также не доступен TLS- *Безопасность* .</span><span class="sxs-lookup"><span data-stu-id="93aa4-108">Note that you cannot have *Simple Authentication and Security Layer* (SASL) **unless** *Transport Layer Security* (TLS) is also available.</span></span> <span data-ttu-id="93aa4-109">SASL отправляется в незашифрованном (читаемом) формате, и его не следует передавать, если только они не защищены другим способом, например TLS.</span><span class="sxs-lookup"><span data-stu-id="93aa4-109">SASL is sent in an unencrypted (readable) format and should never be transmitted unless protected by another means, such as TLS.</span></span>

### <a name="common-xmpp-federation-negotiation-methods"></a><span data-ttu-id="93aa4-110">Распространенные методы согласования КСМПП Федерации</span><span class="sxs-lookup"><span data-stu-id="93aa4-110">Common XMPP Federation Negotiation Methods</span></span>

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
<th><span data-ttu-id="93aa4-111">Безопасность уровня транспорта (TLS)</span><span class="sxs-lookup"><span data-stu-id="93aa4-111">Transport Layer Security (TLS)</span></span></th>
<th><span data-ttu-id="93aa4-112">Простая проверка подлинности и уровень безопасности (SASL)</span><span class="sxs-lookup"><span data-stu-id="93aa4-112">Simple Authentication and Security Layer (SASL)</span></span></th>
<th><span data-ttu-id="93aa4-113">Проверка подлинности диалбакк</span><span class="sxs-lookup"><span data-stu-id="93aa4-113">Dialback Authentication</span></span></th>
<th><span data-ttu-id="93aa4-114">Ожидаемый метод проверки подлинности (-ов)</span><span class="sxs-lookup"><span data-stu-id="93aa4-114">Expected Authentication Method(s)</span></span></th>
<th><span data-ttu-id="93aa4-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="93aa4-115">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="93aa4-116"> Обязательно</span><span class="sxs-lookup"><span data-stu-id="93aa4-116">Required</span></span></p></td>
<td><p><span data-ttu-id="93aa4-117">Обязательно</span><span class="sxs-lookup"><span data-stu-id="93aa4-117">Required</span></span></p></td>
<td><p><span data-ttu-id="93aa4-118">False</span><span class="sxs-lookup"><span data-stu-id="93aa4-118">False</span></span></p></td>
<td><p><span data-ttu-id="93aa4-119">SASL по протоколу TLS</span><span class="sxs-lookup"><span data-stu-id="93aa4-119">SASL over TLS</span></span></p></td>
<td><p><span data-ttu-id="93aa4-120">TLS и SASL должны обеспечивать безопасность потока сообщений SASL.</span><span class="sxs-lookup"><span data-stu-id="93aa4-120">TLS and SASL required helps to ensure that the SASL message stream is secure.</span></span> <span data-ttu-id="93aa4-121">Диалбакк недоступен и не может использоваться для резервного метода в том случае, если для федеративного партнера КСМПП не задано обязательное или необязательное значение TLS.</span><span class="sxs-lookup"><span data-stu-id="93aa4-121">Dialback is not available and cannot be used for a fallback method if the XMPP federated partner has not set TLS to required or optional.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93aa4-122">Обязательно</span><span class="sxs-lookup"><span data-stu-id="93aa4-122">Required</span></span></p></td>
<td><p><span data-ttu-id="93aa4-123">Необязательно </span><span class="sxs-lookup"><span data-stu-id="93aa4-123">Optional</span></span></p></td>
<td><p><span data-ttu-id="93aa4-124">True</span><span class="sxs-lookup"><span data-stu-id="93aa4-124">True</span></span></p></td>
<td><p><span data-ttu-id="93aa4-125">SASL over TLS, TLS Диалбакк, TCP Диалбакк</span><span class="sxs-lookup"><span data-stu-id="93aa4-125">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="93aa4-126">Если для федеративного партнера КСМПП задано значение SASL для необязательного или требуемого SASL, используется TLS.</span><span class="sxs-lookup"><span data-stu-id="93aa4-126">By requiring TLS, if the XMPP federated partner has set SASL to optional or required SASL is used.</span></span> <span data-ttu-id="93aa4-127">Если SASL недоступен, будет использоваться Диалбакк по TLS.</span><span class="sxs-lookup"><span data-stu-id="93aa4-127">If SASL is not available, Dialback over TLS will be used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93aa4-128">Необязательно </span><span class="sxs-lookup"><span data-stu-id="93aa4-128">Optional</span></span></p></td>
<td><p><span data-ttu-id="93aa4-129">Необязательно</span><span class="sxs-lookup"><span data-stu-id="93aa4-129">Optional</span></span></p></td>
<td><p><span data-ttu-id="93aa4-130">True</span><span class="sxs-lookup"><span data-stu-id="93aa4-130">True</span></span></p></td>
<td><p><span data-ttu-id="93aa4-131">SASL over TLS, TLS Диалбакк, TCP Диалбакк</span><span class="sxs-lookup"><span data-stu-id="93aa4-131">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="93aa4-132">Несмотря на то, что предлагаемые методы согласования очень гибки, эти параметры основываются на параметрах партнера КСМПП Федерации.</span><span class="sxs-lookup"><span data-stu-id="93aa4-132">While very flexible in the negotiation methods offered, these settings rely on the XMPP federation partner’s settings.</span></span> <span data-ttu-id="93aa4-133">Если у партнера есть TLS, необязательный или обязательный, но SASL не поддерживается, TLS Диалбакк будет доступен.</span><span class="sxs-lookup"><span data-stu-id="93aa4-133">If the partner has TLS optional or required but SASL is not supported, TLS Dialback will be available.</span></span> <span data-ttu-id="93aa4-134">Если у партнера есть TLS и SASL, для которых установлен необязательный или обязательный вариант, используется оптимальный выбор TLS более SASL.</span><span class="sxs-lookup"><span data-stu-id="93aa4-134">If the partner has TLS and SASL set to optional or required, the optimal selection of TLS over SASL is used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93aa4-135">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="93aa4-135">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="93aa4-136">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="93aa4-136">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="93aa4-137">True</span><span class="sxs-lookup"><span data-stu-id="93aa4-137">True</span></span></p></td>
<td><p><span data-ttu-id="93aa4-138">TCP Диалбакк</span><span class="sxs-lookup"><span data-stu-id="93aa4-138">TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="93aa4-139">Во многих случаях TCP Диалбакк является единственным возможным решением.</span><span class="sxs-lookup"><span data-stu-id="93aa4-139">In many cases, TCP Dialback is the only possible solution.</span></span> <span data-ttu-id="93aa4-140">Менее предпочтительнее, чем другие параметры, она обеспечивает некоторый уровень доверия.</span><span class="sxs-lookup"><span data-stu-id="93aa4-140">Less desirable than other options, it does provide some level of trust.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="xmpp-federation-negotiation-methods-matrix---complete"></a><span data-ttu-id="93aa4-141">Матрица методов согласования КСМПП Федерации — завершено</span><span class="sxs-lookup"><span data-stu-id="93aa4-141">XMPP Federation Negotiation Methods Matrix - Complete</span></span>

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
<th><span data-ttu-id="93aa4-142">Безопасность уровня транспорта (TLS)</span><span class="sxs-lookup"><span data-stu-id="93aa4-142">Transport Layer Security (TLS)</span></span></th>
<th><span data-ttu-id="93aa4-143">Простая проверка подлинности и уровень безопасности (SASL)</span><span class="sxs-lookup"><span data-stu-id="93aa4-143">Simple Authentication and Security Layer (SASL)</span></span></th>
<th><span data-ttu-id="93aa4-144">Проверка подлинности диалбакк</span><span class="sxs-lookup"><span data-stu-id="93aa4-144">Dialback Authentication</span></span></th>
<th><span data-ttu-id="93aa4-145">Ожидаемый метод проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="93aa4-145">Expected Authentication Method</span></span></th>
<th><span data-ttu-id="93aa4-146">Заметки, предупреждение или ошибка для недействительной конфигурации</span><span class="sxs-lookup"><span data-stu-id="93aa4-146">Notes, Warning or Error for Not Valid Configuration</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="93aa4-147"> Обязательно</span><span class="sxs-lookup"><span data-stu-id="93aa4-147">Required</span></span></p></td>
<td><p><span data-ttu-id="93aa4-148">Обязательно</span><span class="sxs-lookup"><span data-stu-id="93aa4-148">Required</span></span></p></td>
<td><p><span data-ttu-id="93aa4-149">True</span><span class="sxs-lookup"><span data-stu-id="93aa4-149">True</span></span></p></td>
<td><p><span data-ttu-id="93aa4-150">SASL по протоколу TLS</span><span class="sxs-lookup"><span data-stu-id="93aa4-150">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="93aa4-151">Диалбакк не будет работать, если требуются оба SASL и TLS.</span><span class="sxs-lookup"><span data-stu-id="93aa4-151">Dialback will not operate if both SASL and TLS are required.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93aa4-152"> Обязательно</span><span class="sxs-lookup"><span data-stu-id="93aa4-152">Required</span></span></p></td>
<td><p><span data-ttu-id="93aa4-153">Обязательно</span><span class="sxs-lookup"><span data-stu-id="93aa4-153">Required</span></span></p></td>
<td><p><span data-ttu-id="93aa4-154">False</span><span class="sxs-lookup"><span data-stu-id="93aa4-154">False</span></span></p></td>
<td><p><span data-ttu-id="93aa4-155">SASL по протоколу TLS</span><span class="sxs-lookup"><span data-stu-id="93aa4-155">SASL over TLS</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93aa4-156">Необязательно </span><span class="sxs-lookup"><span data-stu-id="93aa4-156">Optional</span></span></p></td>
<td><p><span data-ttu-id="93aa4-157">Обязательно</span><span class="sxs-lookup"><span data-stu-id="93aa4-157">Required</span></span></p></td>
<td><p><span data-ttu-id="93aa4-158">True</span><span class="sxs-lookup"><span data-stu-id="93aa4-158">True</span></span></p></td>
<td><p><span data-ttu-id="93aa4-159">SASL over TLS, TLS Диалбакк, TCP Диалбакк</span><span class="sxs-lookup"><span data-stu-id="93aa4-159">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="93aa4-160">Для SASL требуется TLS.</span><span class="sxs-lookup"><span data-stu-id="93aa4-160">SASL requires TLS.</span></span> <span data-ttu-id="93aa4-161">Если вы разрешаете использовать TLS, может возникнуть сбой согласования сеанса.</span><span class="sxs-lookup"><span data-stu-id="93aa4-161">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93aa4-162">Необязательно </span><span class="sxs-lookup"><span data-stu-id="93aa4-162">Optional</span></span></p></td>
<td><p><span data-ttu-id="93aa4-163">Обязательно</span><span class="sxs-lookup"><span data-stu-id="93aa4-163">Required</span></span></p></td>
<td><p><span data-ttu-id="93aa4-164">False</span><span class="sxs-lookup"><span data-stu-id="93aa4-164">False</span></span></p></td>
<td><p><span data-ttu-id="93aa4-165">SASL по протоколу TLS</span><span class="sxs-lookup"><span data-stu-id="93aa4-165">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="93aa4-166">Для SASL требуется TLS.</span><span class="sxs-lookup"><span data-stu-id="93aa4-166">SASL requires TLS.</span></span> <span data-ttu-id="93aa4-167">Если вы разрешаете использовать TLS, может возникнуть сбой согласования сеанса.</span><span class="sxs-lookup"><span data-stu-id="93aa4-167">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93aa4-168">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="93aa4-168">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="93aa4-169">Обязательно</span><span class="sxs-lookup"><span data-stu-id="93aa4-169">Required</span></span></p></td>
<td><p><span data-ttu-id="93aa4-170">True</span><span class="sxs-lookup"><span data-stu-id="93aa4-170">True</span></span></p></td>
<td><p><span data-ttu-id="93aa4-171">TCP Диалбакк</span><span class="sxs-lookup"><span data-stu-id="93aa4-171">TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="93aa4-172">Для SASL требуется TLS.</span><span class="sxs-lookup"><span data-stu-id="93aa4-172">SASL requires TLS.</span></span> <span data-ttu-id="93aa4-173">Если вы разрешаете использовать TLS, может возникнуть сбой согласования сеанса.</span><span class="sxs-lookup"><span data-stu-id="93aa4-173">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93aa4-174">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="93aa4-174">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="93aa4-175">Обязательно</span><span class="sxs-lookup"><span data-stu-id="93aa4-175">Required</span></span></p></td>
<td><p><span data-ttu-id="93aa4-176">False</span><span class="sxs-lookup"><span data-stu-id="93aa4-176">False</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="93aa4-177">Недействительная конфигурация</span><span class="sxs-lookup"><span data-stu-id="93aa4-177">Not Valid Configuration</span></span>


</div></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="93aa4-178">Так как для SASL требуется протокол TLS, а протокол TLS недоступен, SASL/TLS выполнить не удастся.</span><span class="sxs-lookup"><span data-stu-id="93aa4-178">Because SASL requires TLS, and TLS is not available, SASL/TLS cannot succeed.</span></span> <span data-ttu-id="93aa4-179">Для TCP Диалбакк задано значение false, и его нельзя использовать.</span><span class="sxs-lookup"><span data-stu-id="93aa4-179">TCP Dialback is set to false, and cannot be used.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93aa4-180">Обязательно</span><span class="sxs-lookup"><span data-stu-id="93aa4-180">Required</span></span></p></td>
<td><p><span data-ttu-id="93aa4-181">Необязательно </span><span class="sxs-lookup"><span data-stu-id="93aa4-181">Optional</span></span></p></td>
<td><p><span data-ttu-id="93aa4-182">True</span><span class="sxs-lookup"><span data-stu-id="93aa4-182">True</span></span></p></td>
<td><p><span data-ttu-id="93aa4-183">SASL over TLS, Диалбакк TLS</span><span class="sxs-lookup"><span data-stu-id="93aa4-183">SASL over TLS, TLS Dialback</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93aa4-184">Обязательно</span><span class="sxs-lookup"><span data-stu-id="93aa4-184">Required</span></span></p></td>
<td><p><span data-ttu-id="93aa4-185">Необязательно </span><span class="sxs-lookup"><span data-stu-id="93aa4-185">Optional</span></span></p></td>
<td><p><span data-ttu-id="93aa4-186">False</span><span class="sxs-lookup"><span data-stu-id="93aa4-186">False</span></span></p></td>
<td><p><span data-ttu-id="93aa4-187">SASL по протоколу TLS</span><span class="sxs-lookup"><span data-stu-id="93aa4-187">SASL over TLS</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93aa4-188">Необязательно </span><span class="sxs-lookup"><span data-stu-id="93aa4-188">Optional</span></span></p></td>
<td><p><span data-ttu-id="93aa4-189">Необязательно</span><span class="sxs-lookup"><span data-stu-id="93aa4-189">Optional</span></span></p></td>
<td><p><span data-ttu-id="93aa4-190">True</span><span class="sxs-lookup"><span data-stu-id="93aa4-190">True</span></span></p></td>
<td><p><span data-ttu-id="93aa4-191">SASL over TLS, TLS Диалбакк, TCP Диалбакк</span><span class="sxs-lookup"><span data-stu-id="93aa4-191">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="93aa4-192">Для SASL требуется TLS.</span><span class="sxs-lookup"><span data-stu-id="93aa4-192">SASL requires TLS.</span></span> <span data-ttu-id="93aa4-193">Если вы разрешаете использовать TLS, может возникнуть сбой согласования сеанса.</span><span class="sxs-lookup"><span data-stu-id="93aa4-193">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93aa4-194">Необязательно </span><span class="sxs-lookup"><span data-stu-id="93aa4-194">Optional</span></span></p></td>
<td><p><span data-ttu-id="93aa4-195">Необязательно</span><span class="sxs-lookup"><span data-stu-id="93aa4-195">Optional</span></span></p></td>
<td><p><span data-ttu-id="93aa4-196">False</span><span class="sxs-lookup"><span data-stu-id="93aa4-196">False</span></span></p></td>
<td><p><span data-ttu-id="93aa4-197">SASL по протоколу TLS</span><span class="sxs-lookup"><span data-stu-id="93aa4-197">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="93aa4-198">Для SASL требуется TLS.</span><span class="sxs-lookup"><span data-stu-id="93aa4-198">SASL requires TLS.</span></span> <span data-ttu-id="93aa4-199">Если вы разрешаете использовать TLS, может возникнуть сбой согласования сеанса.</span><span class="sxs-lookup"><span data-stu-id="93aa4-199">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93aa4-200">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="93aa4-200">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="93aa4-201">Необязательно </span><span class="sxs-lookup"><span data-stu-id="93aa4-201">Optional</span></span></p></td>
<td><p><span data-ttu-id="93aa4-202">True</span><span class="sxs-lookup"><span data-stu-id="93aa4-202">True</span></span></p></td>
<td><p><span data-ttu-id="93aa4-203">TCP Диалбакк</span><span class="sxs-lookup"><span data-stu-id="93aa4-203">TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="93aa4-204">Для SASL требуется TLS.</span><span class="sxs-lookup"><span data-stu-id="93aa4-204">SASL requires TLS.</span></span> <span data-ttu-id="93aa4-205">Если вы разрешаете использовать TLS, может возникнуть сбой согласования сеанса.</span><span class="sxs-lookup"><span data-stu-id="93aa4-205">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93aa4-206">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="93aa4-206">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="93aa4-207">Необязательно </span><span class="sxs-lookup"><span data-stu-id="93aa4-207">Optional</span></span></p></td>
<td><p><span data-ttu-id="93aa4-208">False</span><span class="sxs-lookup"><span data-stu-id="93aa4-208">False</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="93aa4-209">Недействительная конфигурация</span><span class="sxs-lookup"><span data-stu-id="93aa4-209">Not Valid Configuration</span></span>


</div></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="93aa4-210">Для SASL требуется TLS.</span><span class="sxs-lookup"><span data-stu-id="93aa4-210">SASL requires TLS.</span></span> <span data-ttu-id="93aa4-211">Если вы разрешаете использовать TLS, может возникнуть сбой согласования сеанса.</span><span class="sxs-lookup"><span data-stu-id="93aa4-211">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93aa4-212">Обязательно</span><span class="sxs-lookup"><span data-stu-id="93aa4-212">Required</span></span></p></td>
<td><p><span data-ttu-id="93aa4-213">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="93aa4-213">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="93aa4-214">True</span><span class="sxs-lookup"><span data-stu-id="93aa4-214">True</span></span></p></td>
<td><p><span data-ttu-id="93aa4-215">TLS Диалбакк</span><span class="sxs-lookup"><span data-stu-id="93aa4-215">TLS Dialback</span></span></p></td>
<td><p><span data-ttu-id="93aa4-216">Настройка позволяет TLS Диалбакк.</span><span class="sxs-lookup"><span data-stu-id="93aa4-216">Configuration allows for TLS Dialback.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93aa4-217">Обязательно</span><span class="sxs-lookup"><span data-stu-id="93aa4-217">Required</span></span></p></td>
<td><p><span data-ttu-id="93aa4-218">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="93aa4-218">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="93aa4-219">False</span><span class="sxs-lookup"><span data-stu-id="93aa4-219">False</span></span></p></td>
<td><p><span data-ttu-id="93aa4-220">Недействительная конфигурация</span><span class="sxs-lookup"><span data-stu-id="93aa4-220">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="93aa4-221">Необходимо включить SASL или Диалбакк.</span><span class="sxs-lookup"><span data-stu-id="93aa4-221">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93aa4-222">Необязательно </span><span class="sxs-lookup"><span data-stu-id="93aa4-222">Optional</span></span></p></td>
<td><p><span data-ttu-id="93aa4-223">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="93aa4-223">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="93aa4-224">True</span><span class="sxs-lookup"><span data-stu-id="93aa4-224">True</span></span></p></td>
<td><p><span data-ttu-id="93aa4-225">TLS Диалбакк, TCP Диалбакк</span><span class="sxs-lookup"><span data-stu-id="93aa4-225">TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="93aa4-226">На основе вариантов согласования для другой конечной точки, TCP или TLS Диалбакк будут приняты.</span><span class="sxs-lookup"><span data-stu-id="93aa4-226">Based on negotiation choices of the other end point, TCP or TLS Dialback will be accepted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93aa4-227">Необязательно </span><span class="sxs-lookup"><span data-stu-id="93aa4-227">Optional</span></span></p></td>
<td><p><span data-ttu-id="93aa4-228">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="93aa4-228">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="93aa4-229">False</span><span class="sxs-lookup"><span data-stu-id="93aa4-229">False</span></span></p></td>
<td><p><span data-ttu-id="93aa4-230">Недействительная конфигурация</span><span class="sxs-lookup"><span data-stu-id="93aa4-230">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="93aa4-231">Необходимо включить SASL или Диалбакк.</span><span class="sxs-lookup"><span data-stu-id="93aa4-231">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93aa4-232">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="93aa4-232">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="93aa4-233">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="93aa4-233">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="93aa4-234">True</span><span class="sxs-lookup"><span data-stu-id="93aa4-234">True</span></span></p></td>
<td><p><span data-ttu-id="93aa4-235">TCP Диалбакк</span><span class="sxs-lookup"><span data-stu-id="93aa4-235">TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="93aa4-236">Протокол TCP Диалбакк является единственным доступным способом согласования</span><span class="sxs-lookup"><span data-stu-id="93aa4-236">TCP Dialback is the only negotiation method available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93aa4-237">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="93aa4-237">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="93aa4-238">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="93aa4-238">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="93aa4-239">False</span><span class="sxs-lookup"><span data-stu-id="93aa4-239">False</span></span></p></td>
<td><p><span data-ttu-id="93aa4-240">Недействительная конфигурация</span><span class="sxs-lookup"><span data-stu-id="93aa4-240">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="93aa4-241">Необходимо включить SASL или Диалбакк.</span><span class="sxs-lookup"><span data-stu-id="93aa4-241">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

