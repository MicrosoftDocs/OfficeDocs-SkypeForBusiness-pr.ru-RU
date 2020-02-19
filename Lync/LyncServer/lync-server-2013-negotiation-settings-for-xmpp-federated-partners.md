---
title: 'Lync Server 2013: параметры согласования для федеративных партнеров XMPP'
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
ms.openlocfilehash: 59cae91ac3c0106d7c1a1aa31e0ee4f2549b49c1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42129652"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="negotiation-settings-for-xmpp-federated-partners-in-lync-server-2013"></a><span data-ttu-id="54c59-102">Параметры согласования для федеративных партнеров XMPP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54c59-102">Negotiation settings for XMPP federated partners in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="54c59-103">_**Последнее изменение темы:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="54c59-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="54c59-104">В конфигурации XMPP-партнера доступно значительное количество возможных комбинаций параметров для типов согласования.</span><span class="sxs-lookup"><span data-stu-id="54c59-104">The settings for the negotiation types in the configuration of an XMPP Partner have a wide variety of possible combinations.</span></span> <span data-ttu-id="54c59-105">Но не все эти комбинации являются допустимыми.</span><span class="sxs-lookup"><span data-stu-id="54c59-105">Not all of these combinations are valid.</span></span> <span data-ttu-id="54c59-106">В приведенной здесь таблице подробно описывается, какие параметры являются допустимыми, а какие — нет.</span><span class="sxs-lookup"><span data-stu-id="54c59-106">The table detailed in this topic will define the valid and not valid settings.</span></span> <span data-ttu-id="54c59-107">Распространенные конфигурации представлены в первой таблице, во второй таблице приведены все возможные комбинации.</span><span class="sxs-lookup"><span data-stu-id="54c59-107">Common configurations are presented in the first table, the second table detailing all possible combinations.</span></span> <span data-ttu-id="54c59-108">Обратите внимание на то, что вы не можете использовать *простую проверку подлинности и уровень безопасности* (SASL), **если** также не доступен протокол TLS ( *Transport Layer Security* ).</span><span class="sxs-lookup"><span data-stu-id="54c59-108">Note that you cannot have *Simple Authentication and Security Layer* (SASL) **unless** *Transport Layer Security* (TLS) is also available.</span></span> <span data-ttu-id="54c59-109">Данные SASL отправляются в незашифрованном (пригодном для чтения) формате, поэтому при их передаче следует использовать другие средства защиты, такие как TLS.</span><span class="sxs-lookup"><span data-stu-id="54c59-109">SASL is sent in an unencrypted (readable) format and should never be transmitted unless protected by another means, such as TLS.</span></span>

### <a name="common-xmpp-federation-negotiation-methods"></a><span data-ttu-id="54c59-110">Распространенные методы согласования федерации XMPP</span><span class="sxs-lookup"><span data-stu-id="54c59-110">Common XMPP Federation Negotiation Methods</span></span>

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
<th><span data-ttu-id="54c59-111">TLS (Transport Layer Security)</span><span class="sxs-lookup"><span data-stu-id="54c59-111">Transport Layer Security (TLS)</span></span></th>
<th><span data-ttu-id="54c59-112">SASL (Simple Authentication and Security Layer)</span><span class="sxs-lookup"><span data-stu-id="54c59-112">Simple Authentication and Security Layer (SASL)</span></span></th>
<th><span data-ttu-id="54c59-113">Проверка подлинности с обратным вызовом</span><span class="sxs-lookup"><span data-stu-id="54c59-113">Dialback Authentication</span></span></th>
<th><span data-ttu-id="54c59-114">Ожидаемые методы проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="54c59-114">Expected Authentication Method(s)</span></span></th>
<th><span data-ttu-id="54c59-115">Notes</span><span class="sxs-lookup"><span data-stu-id="54c59-115">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="54c59-116">Обязательный</span><span class="sxs-lookup"><span data-stu-id="54c59-116">Required</span></span></p></td>
<td><p><span data-ttu-id="54c59-117">Обязательный</span><span class="sxs-lookup"><span data-stu-id="54c59-117">Required</span></span></p></td>
<td><p><span data-ttu-id="54c59-118">False</span><span class="sxs-lookup"><span data-stu-id="54c59-118">False</span></span></p></td>
<td><p><span data-ttu-id="54c59-119">SASL через TLS</span><span class="sxs-lookup"><span data-stu-id="54c59-119">SASL over TLS</span></span></p></td>
<td><p><span data-ttu-id="54c59-p102">Обязательное использование TLS и SASL помогает обеспечить безопасность потока сообщений SASL. Обратный вызов недоступен и не может применяться в качестве резервного метода, если федеративный XMPP-партнер не установил обязательное или необязательное использование TLS.</span><span class="sxs-lookup"><span data-stu-id="54c59-p102">TLS and SASL required helps to ensure that the SASL message stream is secure. Dialback is not available and cannot be used for a fallback method if the XMPP federated partner has not set TLS to required or optional.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54c59-122">Обязательна</span><span class="sxs-lookup"><span data-stu-id="54c59-122">Required</span></span></p></td>
<td><p><span data-ttu-id="54c59-123">Необязательный</span><span class="sxs-lookup"><span data-stu-id="54c59-123">Optional</span></span></p></td>
<td><p><span data-ttu-id="54c59-124">Верно</span><span class="sxs-lookup"><span data-stu-id="54c59-124">True</span></span></p></td>
<td><p><span data-ttu-id="54c59-125">SASL через TLS, обратный вызов TLS, обратный вызов TCP</span><span class="sxs-lookup"><span data-stu-id="54c59-125">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="54c59-p103">Если федеративный XMPP-партнер установил обязательное или необязательное использование SASL, в случае обязательного использования TLS применяется SASL. Если SASL недоступен, используется обратный вызов через TLS.</span><span class="sxs-lookup"><span data-stu-id="54c59-p103">By requiring TLS, if the XMPP federated partner has set SASL to optional or required SASL is used. If SASL is not available, Dialback over TLS will be used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54c59-128">Необязательный</span><span class="sxs-lookup"><span data-stu-id="54c59-128">Optional</span></span></p></td>
<td><p><span data-ttu-id="54c59-129">Необязательна</span><span class="sxs-lookup"><span data-stu-id="54c59-129">Optional</span></span></p></td>
<td><p><span data-ttu-id="54c59-130">Верно</span><span class="sxs-lookup"><span data-stu-id="54c59-130">True</span></span></p></td>
<td><p><span data-ttu-id="54c59-131">SASL через TLS, обратный вызов TLS, обратный вызов TCP</span><span class="sxs-lookup"><span data-stu-id="54c59-131">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="54c59-p104">Хотя эти параметры и обеспечивают гибкость с точки зрения доступных методов согласования, они основаны на параметрах XMPP-партнера федерации. Если партнер задает обязательное или необязательное использование TLS, но SASL не поддерживается, будет доступен обратный вызов через TLS. Если партнер задает обязательное или необязательное использование TLS и SASL, используется оптимальный вариант TLS через SASL.</span><span class="sxs-lookup"><span data-stu-id="54c59-p104">While very flexible in the negotiation methods offered, these settings rely on the XMPP federation partner’s settings. If the partner has TLS optional or required but SASL is not supported, TLS Dialback will be available. If the partner has TLS and SASL set to optional or required, the optimal selection of TLS over SASL is used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54c59-135">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="54c59-135">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="54c59-136">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="54c59-136">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="54c59-137">Верно</span><span class="sxs-lookup"><span data-stu-id="54c59-137">True</span></span></p></td>
<td><p><span data-ttu-id="54c59-138">Обратный вызов TCP</span><span class="sxs-lookup"><span data-stu-id="54c59-138">TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="54c59-p105">Во многих случаях обратный вызов TCP является единственным возможным решением и обеспечивает некоторый уровень доверия, хотя желательно использовать другие варианты.</span><span class="sxs-lookup"><span data-stu-id="54c59-p105">In many cases, TCP Dialback is the only possible solution. Less desirable than other options, it does provide some level of trust.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="xmpp-federation-negotiation-methods-matrix---complete"></a><span data-ttu-id="54c59-141">Полная матрица методов согласования федерации XMPP</span><span class="sxs-lookup"><span data-stu-id="54c59-141">XMPP Federation Negotiation Methods Matrix - Complete</span></span>

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
<th><span data-ttu-id="54c59-142">TLS (Transport Layer Security)</span><span class="sxs-lookup"><span data-stu-id="54c59-142">Transport Layer Security (TLS)</span></span></th>
<th><span data-ttu-id="54c59-143">SASL (Simple Authentication and Security Layer)</span><span class="sxs-lookup"><span data-stu-id="54c59-143">Simple Authentication and Security Layer (SASL)</span></span></th>
<th><span data-ttu-id="54c59-144">Проверка подлинности с обратным вызовом</span><span class="sxs-lookup"><span data-stu-id="54c59-144">Dialback Authentication</span></span></th>
<th><span data-ttu-id="54c59-145">Ожидаемый метод проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="54c59-145">Expected Authentication Method</span></span></th>
<th><span data-ttu-id="54c59-146">Примечания, предупреждение или ошибка для недействительной конфигурации</span><span class="sxs-lookup"><span data-stu-id="54c59-146">Notes, Warning or Error for Not Valid Configuration</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="54c59-147">Обязательный</span><span class="sxs-lookup"><span data-stu-id="54c59-147">Required</span></span></p></td>
<td><p><span data-ttu-id="54c59-148">Обязательный</span><span class="sxs-lookup"><span data-stu-id="54c59-148">Required</span></span></p></td>
<td><p><span data-ttu-id="54c59-149">Верно</span><span class="sxs-lookup"><span data-stu-id="54c59-149">True</span></span></p></td>
<td><p><span data-ttu-id="54c59-150">SASL через TLS</span><span class="sxs-lookup"><span data-stu-id="54c59-150">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="54c59-151">Обратный вызов не будет работать, если требуется как SASL, так и TLS.</span><span class="sxs-lookup"><span data-stu-id="54c59-151">Dialback will not operate if both SASL and TLS are required.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54c59-152">Обязательный</span><span class="sxs-lookup"><span data-stu-id="54c59-152">Required</span></span></p></td>
<td><p><span data-ttu-id="54c59-153">Обязательный</span><span class="sxs-lookup"><span data-stu-id="54c59-153">Required</span></span></p></td>
<td><p><span data-ttu-id="54c59-154">False</span><span class="sxs-lookup"><span data-stu-id="54c59-154">False</span></span></p></td>
<td><p><span data-ttu-id="54c59-155">SASL через TLS</span><span class="sxs-lookup"><span data-stu-id="54c59-155">SASL over TLS</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54c59-156">Необязательна</span><span class="sxs-lookup"><span data-stu-id="54c59-156">Optional</span></span></p></td>
<td><p><span data-ttu-id="54c59-157">Обязательна</span><span class="sxs-lookup"><span data-stu-id="54c59-157">Required</span></span></p></td>
<td><p><span data-ttu-id="54c59-158">Верно</span><span class="sxs-lookup"><span data-stu-id="54c59-158">True</span></span></p></td>
<td><p><span data-ttu-id="54c59-159">SASL через TLS, обратный вызов TLS, обратный вызов TCP</span><span class="sxs-lookup"><span data-stu-id="54c59-159">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="54c59-160">Для SASL требуется TLS.</span><span class="sxs-lookup"><span data-stu-id="54c59-160">SASL requires TLS.</span></span> <span data-ttu-id="54c59-161">Включение необязательного использования TLS может привести к сбою согласования сеансов.</span><span class="sxs-lookup"><span data-stu-id="54c59-161">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54c59-162">Необязательна</span><span class="sxs-lookup"><span data-stu-id="54c59-162">Optional</span></span></p></td>
<td><p><span data-ttu-id="54c59-163">Обязательна</span><span class="sxs-lookup"><span data-stu-id="54c59-163">Required</span></span></p></td>
<td><p><span data-ttu-id="54c59-164">False</span><span class="sxs-lookup"><span data-stu-id="54c59-164">False</span></span></p></td>
<td><p><span data-ttu-id="54c59-165">SASL через TLS</span><span class="sxs-lookup"><span data-stu-id="54c59-165">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="54c59-166">Для SASL требуется TLS.</span><span class="sxs-lookup"><span data-stu-id="54c59-166">SASL requires TLS.</span></span> <span data-ttu-id="54c59-167">Включение необязательного использования TLS может привести к сбою согласования сеансов.</span><span class="sxs-lookup"><span data-stu-id="54c59-167">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54c59-168">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="54c59-168">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="54c59-169">Обязательна</span><span class="sxs-lookup"><span data-stu-id="54c59-169">Required</span></span></p></td>
<td><p><span data-ttu-id="54c59-170">Верно</span><span class="sxs-lookup"><span data-stu-id="54c59-170">True</span></span></p></td>
<td><p><span data-ttu-id="54c59-171">Обратный вызов TCP</span><span class="sxs-lookup"><span data-stu-id="54c59-171">TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="54c59-172">Для SASL требуется TLS.</span><span class="sxs-lookup"><span data-stu-id="54c59-172">SASL requires TLS.</span></span> <span data-ttu-id="54c59-173">Включение необязательного использования TLS может привести к сбою согласования сеансов.</span><span class="sxs-lookup"><span data-stu-id="54c59-173">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54c59-174">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="54c59-174">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="54c59-175">Обязательна</span><span class="sxs-lookup"><span data-stu-id="54c59-175">Required</span></span></p></td>
<td><p><span data-ttu-id="54c59-176">False</span><span class="sxs-lookup"><span data-stu-id="54c59-176">False</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="54c59-177">Недопустимая конфигурация</span><span class="sxs-lookup"><span data-stu-id="54c59-177">Not Valid Configuration</span></span>


</div></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="54c59-p109">Поскольку для SASL требуется TLS, который недоступен, комбинация SASL/TLS не работает. Для обратного вызова TCP устанавливается недопустимое состояние, и данный метод использовать нельзя.</span><span class="sxs-lookup"><span data-stu-id="54c59-p109">Because SASL requires TLS, and TLS is not available, SASL/TLS cannot succeed. TCP Dialback is set to false, and cannot be used.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54c59-180">Обязательна</span><span class="sxs-lookup"><span data-stu-id="54c59-180">Required</span></span></p></td>
<td><p><span data-ttu-id="54c59-181">Необязательный</span><span class="sxs-lookup"><span data-stu-id="54c59-181">Optional</span></span></p></td>
<td><p><span data-ttu-id="54c59-182">Верно</span><span class="sxs-lookup"><span data-stu-id="54c59-182">True</span></span></p></td>
<td><p><span data-ttu-id="54c59-183">SASL через TLS, обратный вызов TLS</span><span class="sxs-lookup"><span data-stu-id="54c59-183">SASL over TLS, TLS Dialback</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54c59-184">Обязательна</span><span class="sxs-lookup"><span data-stu-id="54c59-184">Required</span></span></p></td>
<td><p><span data-ttu-id="54c59-185">Необязательный</span><span class="sxs-lookup"><span data-stu-id="54c59-185">Optional</span></span></p></td>
<td><p><span data-ttu-id="54c59-186">False</span><span class="sxs-lookup"><span data-stu-id="54c59-186">False</span></span></p></td>
<td><p><span data-ttu-id="54c59-187">SASL через TLS</span><span class="sxs-lookup"><span data-stu-id="54c59-187">SASL over TLS</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54c59-188">Необязательный</span><span class="sxs-lookup"><span data-stu-id="54c59-188">Optional</span></span></p></td>
<td><p><span data-ttu-id="54c59-189">Необязательна</span><span class="sxs-lookup"><span data-stu-id="54c59-189">Optional</span></span></p></td>
<td><p><span data-ttu-id="54c59-190">Верно</span><span class="sxs-lookup"><span data-stu-id="54c59-190">True</span></span></p></td>
<td><p><span data-ttu-id="54c59-191">SASL через TLS, обратный вызов TLS, обратный вызов TCP</span><span class="sxs-lookup"><span data-stu-id="54c59-191">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="54c59-192">Для SASL требуется TLS.</span><span class="sxs-lookup"><span data-stu-id="54c59-192">SASL requires TLS.</span></span> <span data-ttu-id="54c59-193">Включение необязательного использования TLS может привести к сбою согласования сеансов.</span><span class="sxs-lookup"><span data-stu-id="54c59-193">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54c59-194">Необязательный</span><span class="sxs-lookup"><span data-stu-id="54c59-194">Optional</span></span></p></td>
<td><p><span data-ttu-id="54c59-195">Необязательна</span><span class="sxs-lookup"><span data-stu-id="54c59-195">Optional</span></span></p></td>
<td><p><span data-ttu-id="54c59-196">False</span><span class="sxs-lookup"><span data-stu-id="54c59-196">False</span></span></p></td>
<td><p><span data-ttu-id="54c59-197">SASL через TLS</span><span class="sxs-lookup"><span data-stu-id="54c59-197">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="54c59-198">Для SASL требуется TLS.</span><span class="sxs-lookup"><span data-stu-id="54c59-198">SASL requires TLS.</span></span> <span data-ttu-id="54c59-199">Включение необязательного использования TLS может привести к сбою согласования сеансов.</span><span class="sxs-lookup"><span data-stu-id="54c59-199">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54c59-200">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="54c59-200">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="54c59-201">Необязательна</span><span class="sxs-lookup"><span data-stu-id="54c59-201">Optional</span></span></p></td>
<td><p><span data-ttu-id="54c59-202">Верно</span><span class="sxs-lookup"><span data-stu-id="54c59-202">True</span></span></p></td>
<td><p><span data-ttu-id="54c59-203">Обратный вызов TCP</span><span class="sxs-lookup"><span data-stu-id="54c59-203">TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="54c59-204">Для SASL требуется TLS.</span><span class="sxs-lookup"><span data-stu-id="54c59-204">SASL requires TLS.</span></span> <span data-ttu-id="54c59-205">Включение необязательного использования TLS может привести к сбою согласования сеансов.</span><span class="sxs-lookup"><span data-stu-id="54c59-205">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54c59-206">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="54c59-206">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="54c59-207">Необязательна</span><span class="sxs-lookup"><span data-stu-id="54c59-207">Optional</span></span></p></td>
<td><p><span data-ttu-id="54c59-208">False</span><span class="sxs-lookup"><span data-stu-id="54c59-208">False</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="54c59-209">Недопустимая конфигурация</span><span class="sxs-lookup"><span data-stu-id="54c59-209">Not Valid Configuration</span></span>


</div></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="54c59-p113">Для SASL требуется TLS. Включение необязательного использования TLS может привести к сбою согласования сеансов.</span><span class="sxs-lookup"><span data-stu-id="54c59-p113">SASL requires TLS. Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54c59-212">Обязательна</span><span class="sxs-lookup"><span data-stu-id="54c59-212">Required</span></span></p></td>
<td><p><span data-ttu-id="54c59-213">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="54c59-213">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="54c59-214">Верно</span><span class="sxs-lookup"><span data-stu-id="54c59-214">True</span></span></p></td>
<td><p><span data-ttu-id="54c59-215">Обратный вызов TCP</span><span class="sxs-lookup"><span data-stu-id="54c59-215">TLS Dialback</span></span></p></td>
<td><p><span data-ttu-id="54c59-216">Конфигурация допускает использование обратного вызова TLS.</span><span class="sxs-lookup"><span data-stu-id="54c59-216">Configuration allows for TLS Dialback.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54c59-217">Обязательна</span><span class="sxs-lookup"><span data-stu-id="54c59-217">Required</span></span></p></td>
<td><p><span data-ttu-id="54c59-218">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="54c59-218">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="54c59-219">False</span><span class="sxs-lookup"><span data-stu-id="54c59-219">False</span></span></p></td>
<td><p><span data-ttu-id="54c59-220">Недопустимая конфигурация</span><span class="sxs-lookup"><span data-stu-id="54c59-220">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="54c59-221">Необходимо включить SASL или обратный вызов.</span><span class="sxs-lookup"><span data-stu-id="54c59-221">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54c59-222">Необязательна</span><span class="sxs-lookup"><span data-stu-id="54c59-222">Optional</span></span></p></td>
<td><p><span data-ttu-id="54c59-223">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="54c59-223">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="54c59-224">Верно</span><span class="sxs-lookup"><span data-stu-id="54c59-224">True</span></span></p></td>
<td><p><span data-ttu-id="54c59-225">Обратный вызов TLS, обратный вызов TCP</span><span class="sxs-lookup"><span data-stu-id="54c59-225">TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="54c59-226">В соответствии с вариантами согласования, включенными для другой конечной точки, будет принят обратный вызов TCP или TLS.</span><span class="sxs-lookup"><span data-stu-id="54c59-226">Based on negotiation choices of the other end point, TCP or TLS Dialback will be accepted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54c59-227">Необязательна</span><span class="sxs-lookup"><span data-stu-id="54c59-227">Optional</span></span></p></td>
<td><p><span data-ttu-id="54c59-228">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="54c59-228">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="54c59-229">False</span><span class="sxs-lookup"><span data-stu-id="54c59-229">False</span></span></p></td>
<td><p><span data-ttu-id="54c59-230">Недопустимая конфигурация</span><span class="sxs-lookup"><span data-stu-id="54c59-230">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="54c59-231">Необходимо включить SASL или обратный вызов.</span><span class="sxs-lookup"><span data-stu-id="54c59-231">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54c59-232">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="54c59-232">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="54c59-233">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="54c59-233">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="54c59-234">Верно</span><span class="sxs-lookup"><span data-stu-id="54c59-234">True</span></span></p></td>
<td><p><span data-ttu-id="54c59-235">Обратный вызов TCP</span><span class="sxs-lookup"><span data-stu-id="54c59-235">TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="54c59-236">Обратный вызов TCP является единственным доступным методом согласования</span><span class="sxs-lookup"><span data-stu-id="54c59-236">TCP Dialback is the only negotiation method available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54c59-237">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="54c59-237">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="54c59-238">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="54c59-238">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="54c59-239">False</span><span class="sxs-lookup"><span data-stu-id="54c59-239">False</span></span></p></td>
<td><p><span data-ttu-id="54c59-240">Недопустимая конфигурация</span><span class="sxs-lookup"><span data-stu-id="54c59-240">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="54c59-241">Необходимо включить SASL или обратный вызов.</span><span class="sxs-lookup"><span data-stu-id="54c59-241">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

