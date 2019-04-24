---
title: Изменение существующей политики ПИН-код в Скайп для Business Server
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 517caaee-3349-4fa6-8d86-e4da3258a445
description: 'Сводка: Изменение существующей политики ПИН-код в Скайп для Business Server.'
ms.openlocfilehash: 7694b96b3e3dc169e6642c435edf38506a506bb8
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32217868"
---
# <a name="modify-an-existing-pin-policy-in-skype-for-business-server"></a><span data-ttu-id="c2ba9-103">Изменение существующей политики ПИН-код в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="c2ba9-103">Modify an existing PIN policy in Skype for Business Server</span></span>
 
<span data-ttu-id="c2ba9-104">**Сводка:** Изменение существующей политики ПИН-код в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="c2ba9-104">**Summary:** Modify an existing PIN policy in Skype for Business Server.</span></span>
  
<span data-ttu-id="c2ba9-105">Вкладка **Политики ПИН-КОДОВ** для предоставления персонального идентификационного номера (ПИН-кода), проверки подлинности пользователей, которые подключаются к Скайп для бизнеса с IP-телефонов.</span><span class="sxs-lookup"><span data-stu-id="c2ba9-105">You can use the **PIN Policy** tab to provide personal identification number (PIN) authentication to users who are connecting to Skype for Business with IP Phones.</span></span> <span data-ttu-id="c2ba9-106">Чтобы использовать проверку подлинности по ПИН-коду, необходимо установить флажок **Разрешить проверку подлинности на основе ПИН-кода** в настройках веб-службы.</span><span class="sxs-lookup"><span data-stu-id="c2ba9-106">To use PIN authentication, make sure that **Enable PIN Authentication** is selected in Web Service settings.</span></span>
  
<span data-ttu-id="c2ba9-107">Выполните следующие действия, чтобы изменить политику ПИН-кода на уровне пользователя или узла.</span><span class="sxs-lookup"><span data-stu-id="c2ba9-107">Follow these steps to modify a user-level or a site-level PIN policy.</span></span> 
  
### <a name="to-modify-an-existing-pin-policy"></a><span data-ttu-id="c2ba9-108">Изменение существующей политики ПИН-кода</span><span class="sxs-lookup"><span data-stu-id="c2ba9-108">To modify an existing PIN policy</span></span>

1.  <span data-ttu-id="c2ba9-109">Используя учетную запись пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или роль CsServerAdministrator или CsAdministrator, войдите на любой компьютер, который находится в сети, в котором вы развернули Скайп для Business Server .</span><span class="sxs-lookup"><span data-stu-id="c2ba9-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="c2ba9-110">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="c2ba9-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="c2ba9-111">В левой панели навигации последовательно выберите пункты **Безопасность** и **Политика ПИН-кода**.</span><span class="sxs-lookup"><span data-stu-id="c2ba9-111">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="c2ba9-112">На странице **Политика в отношении ПИН-кодов** выберите политику, нажмите кнопку **Изменить**, а затем щелкните **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="c2ba9-112">On the **PIN Policy** page, click a policy, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="c2ba9-p102">В окне **Изменение политики ПИН-кода** введите или выберите в поле **Минимальная длина ПИН-кода** минимальную длину ПИН-кода. Минимальная длина по умолчанию составляет пять цифр.</span><span class="sxs-lookup"><span data-stu-id="c2ba9-p102">In **Edit PIN Policy**, in **Minimum PIN length**, type or select the minimum PIN length that you want to allow. The default minimum length is five digits.</span></span>
    
6. <span data-ttu-id="c2ba9-p103">Чтобы иметь возможность задать максимальное число попыток входа перед блокированием пользователя, установите флажок **Задать максимальное число попыток входа**. Если этот параметр не выбран, максимальное число разрешенных попыток входа автоматически определяется в зависимости от длины ПИН-кода. По умолчанию максимальное число попыток определяется автоматически.</span><span class="sxs-lookup"><span data-stu-id="c2ba9-p103">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box. If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length. By default, the maximum number of attempts is automatically determined.</span></span>
    
7. <span data-ttu-id="c2ba9-118">Если установлен флажок **Задать максимальное число попыток входа**, в поле **Максимальное число попыток входа** введите или выберите максимальное число попыток входа, которое требуется разрешить.</span><span class="sxs-lookup"><span data-stu-id="c2ba9-118">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>
    
8. <span data-ttu-id="c2ba9-p104">Чтобы ПИН-коды имели конечный срок действия, установите флажок **Включить конечный срок действия ПИН-кодов**. Если этот параметр не выбран, ПИН-коды не будут иметь ограничений по сроку действия. По умолчанию ПИН-коды не имеют ограничений по сроку действия.</span><span class="sxs-lookup"><span data-stu-id="c2ba9-p104">To have PINs expire, select the **Enable PIN expiration** check box. If you do not select this option, PINs will never expire. By default, PINs never expire.</span></span>
    
9. <span data-ttu-id="c2ba9-122">Если флажок **Разрешить окончание срока действия ПИН-кода** установлен, то в поле **Срок действия ПИН-кода истекает после (дней)** введите или выберите максимальное число дней, после которых ПИН-коды становятся недействительными.</span><span class="sxs-lookup"><span data-stu-id="c2ba9-122">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>
    
10. <span data-ttu-id="c2ba9-p105">В поле **История значений ПИН-кода** введите число ПИН-кодов, которое пользователь должен создать перед тем, как он сможет использовать их повторно. По умолчанию пользователи могут повторно использовать ПИН-коды.</span><span class="sxs-lookup"><span data-stu-id="c2ba9-p105">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN. By default, users can reuse their PINs.</span></span>
    
11. <span data-ttu-id="c2ba9-p106">Чтобы разрешить распространенные последовательности цифр в ПИН-кодах, такие как последовательные номера и повторяющиеся наборы номеров, установите флажок **Разрешить общие шаблоны**. Если не выбрать этот параметр, будут разрешены только сложные наборы цифр. По умолчанию разрешены только сложные наборы цифр.</span><span class="sxs-lookup"><span data-stu-id="c2ba9-p106">To allow common patterns of digits in PINs, such as sequential numbers and repetitive sets of numbers, select the **Allow common patterns** check box. If you do not select this option, only complex patterns of digits are allowed. By default, only complex patterns of digits are allowed.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="c2ba9-128">Мы рекомендуем не разрешать использование распространенных последовательностей.</span><span class="sxs-lookup"><span data-stu-id="c2ba9-128">We recommend that you do not allow common patterns.</span></span> 
  
12. <span data-ttu-id="c2ba9-129">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="c2ba9-129">Click **Commit**.</span></span>
    

