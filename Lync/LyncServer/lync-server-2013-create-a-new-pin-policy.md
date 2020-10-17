---
title: 'Lync Server 2013: создание новой политики ПИН-кодов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a new PIN policy
ms:assetid: 8bdf0478-fe9f-4371-93ff-db39381a25db
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182547(v=OCS.15)
ms:contentKeyID: 48184777
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e1755ee6afc6ce613451d1dc17155a4b6c9c744d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501926"
---
# <a name="create-a-new-pin-policy-in-lync-server-2013"></a><span data-ttu-id="44235-102">Создание новой политики ПИН-кодов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44235-102">Create a new PIN policy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="44235-103">_**Последнее изменение темы:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="44235-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="44235-104">С помощью страницы **политика ПИН-кодов** можно предоставить пользователям, подключающимся к Lync 2013 с IP-телефонами, проверку подлинности личного идентификационного номера (ПИН-кода).</span><span class="sxs-lookup"><span data-stu-id="44235-104">You can use the **PIN Policy** page to provide personal identification number (PIN) authentication to users who are connecting to Lync 2013 with IP Phones.</span></span> <span data-ttu-id="44235-105">Чтобы использовать проверку подлинности на основе ПИН-кодов, необходимо установить флажок **Enable PIN Authentication (Включить проверку подлинности на основе ПИН-кодов)** в параметрах веб-службы.</span><span class="sxs-lookup"><span data-stu-id="44235-105">To use PIN authentication, make sure that **Enable PIN Authentication** is selected in Web Service settings.</span></span> <span data-ttu-id="44235-106">Дополнительные сведения: [изменение параметров конфигурации существующей веб-службы в Lync Server 2013](lync-server-2013-modify-existing-web-service-configuration-settings.md).</span><span class="sxs-lookup"><span data-stu-id="44235-106">For details, see [Modify existing Web Service configuration settings in Lync Server 2013](lync-server-2013-modify-existing-web-service-configuration-settings.md).</span></span>

<span data-ttu-id="44235-107">Для создания политики ПИН-кодов на уровне пользователя или сайта выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="44235-107">Follow these steps to create a user-level or a site-level PIN policy.</span></span>

<div>

## <a name="to-create-a-user-or-site-pin-policy"></a><span data-ttu-id="44235-108">Создание политики ПИН-кодов на уровне пользователя или сайта</span><span class="sxs-lookup"><span data-stu-id="44235-108">To create a user or site PIN policy</span></span>

1.  <span data-ttu-id="44235-109">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsServerAdministrator или CsAdministrator, войдите на любой компьютер в сети, в которой развернут Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="44235-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="44235-110">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="44235-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="44235-111">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="44235-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="44235-112">В левой панели навигации последовательно выберите пункты **Security (Безопасность)** и **PIN Policy (Политика ПИН-кодов)**.</span><span class="sxs-lookup"><span data-stu-id="44235-112">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>

4.  <span data-ttu-id="44235-113">На странице **PIN Policy (Политика ПИН-кодов)** нажмите **New (Создать)**, а затем выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="44235-113">On the **PIN Policy** page, click **New**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="44235-p103">Чтобы создать политику на уровне пользователя, выберите пункт **User policy (Политика пользователя)**. В разделе **New PIN Policy (Новая политика ПИН-кодов)**, в поле **Имя** укажите имя, которое описывает эту политику.</span><span class="sxs-lookup"><span data-stu-id="44235-p103">To create a user-level policy, click **User policy**. In **New PIN Policy**, in **Name**, type a name that describes the policy.</span></span>
    
      - <span data-ttu-id="44235-p104">Чтобы создать политику на уровне сайта, выберите пункт **Site policy (Политика сайта)**. В поле поиска **Select a Site (Выбор сайта)** введите имя (или часть имени) сайта, для которого требуется создать политику. В появившемся списке сайтов выберите нужный и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="44235-p104">To create a site-level policy, click **Site policy**. In the **Select a Site** search field, type all or part of the name of the site for which you want to create a policy. In the resulting list of sites, click the site you want, and then click **OK**.</span></span>

5.  <span data-ttu-id="44235-119">В поле **Описание** введите описание этой политики ПИН-кодов.</span><span class="sxs-lookup"><span data-stu-id="44235-119">In the **Description** field, type a description of the PIN policy.</span></span>

6.  <span data-ttu-id="44235-p105">В поле **Minimum PIN length (Минимальная длина ПИН-кода)** введите или выберите минимальную длину ПИН-кода, которую планируется разрешить. По умолчанию минимальная длина — пять цифр.</span><span class="sxs-lookup"><span data-stu-id="44235-p105">In the **Minimum PIN length** field, type or select the minimum PIN length that you want to allow. The default minimum length is five digits.</span></span>

7.  <span data-ttu-id="44235-p106">Чтобы иметь возможность задавать максимальное количество попыток входа до блокировки пользователя, установите флажок **Specify maximum logon attempts (Указать максимальное количество попыток входа)**. Если этот флажок не установить, то максимальное количество разрешенных попыток определяется автоматически на основе длины ПИН-кода. По умолчанию максимальное количество попыток определяется автоматически.</span><span class="sxs-lookup"><span data-stu-id="44235-p106">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box. If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length. By default, the maximum number of attempts is automatically determined.</span></span>

8.  <span data-ttu-id="44235-125">Если флажок **Specify maximum logon attempts (Указать максимальное количество попыток входа)** установлен, в поле **Maximum logon attempts (Максимальное количество попыток входа)** введите или выберите максимальное количество попыток входа, которое планируется разрешить.</span><span class="sxs-lookup"><span data-stu-id="44235-125">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>

9.  <span data-ttu-id="44235-p107">Чтобы ПИН-коды имели конечный срок действия, установите флажок **Enable PIN expiration (Включить окончание срока действия ПИН-кодов)**. Если этот флажок не установить, то ПИН-коды будут бессрочными. По умолчанию ПИН-коды бессрочные.</span><span class="sxs-lookup"><span data-stu-id="44235-p107">To have PINs expire, select the **Enable PIN expiration** check box. If you do not select this option, PINs will never expire. By default, PINs never expire.</span></span>

10. <span data-ttu-id="44235-129">Если флажок **Enable PIN expiration (Включить окончание срока действия ПИН-кодов)** установлен, в поле **PIN expires after (days) (Срок действия ПИН-кода истекает через (в днях)** введите или выберите количество дней, которое ПИН-код будет действительным.</span><span class="sxs-lookup"><span data-stu-id="44235-129">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>

11. <span data-ttu-id="44235-p108">В поле **PIN history count (Счетчик журнала ПИН-кодов)** введите количество ПИН-кодов, которое должен создать пользователь, прежде чем сможет повторно использовать ПИН-код. По умолчанию пользователи могут повторно использовать свои ПИН-коды.</span><span class="sxs-lookup"><span data-stu-id="44235-p108">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN. By default, users can reuse their PINs.</span></span>

12. <span data-ttu-id="44235-p109">Чтобы разрешить простые шаблоны цифр в ПИН-кодах, такие как последовательные или повторяющиеся цифры, установите флажок **Allow common patterns (Разрешить простые шаблоны)**. Если этот флажок не установлен, то разрешены только сложные шаблоны цифр. По умолчанию разрешены только сложные шаблоны.</span><span class="sxs-lookup"><span data-stu-id="44235-p109">To allow common patterns of digits in PINs, such as sequential numbers and repetitive sets of numbers, select the **Allow common patterns** check box. If you do not select this option, only complex patterns of digits are allowed. By default, only complex patterns of digits are allowed.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="44235-135">Рекомендуется не разрешать простые шаблоны.</span><span class="sxs-lookup"><span data-stu-id="44235-135">We recommend that you do not allow common patterns.</span></span>

    
    </div>

13. <span data-ttu-id="44235-136">Нажмите кнопку **Зафиксировать**.</span><span class="sxs-lookup"><span data-stu-id="44235-136">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

