---
title: 'Lync Server 2013: Включение поддержки размещенной голосовой почты для пользователей'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable users for hosted voice mail
ms:assetid: fa559f8f-ef99-43a1-b580-9e998b95efb8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413062(v=OCS.15)
ms:contentKeyID: 48185919
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6dc71125b42fab144b1c6ba15064e84c6be50b57
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138040"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-users-for-hosted-voice-mail-in-lync-server-2013"></a><span data-ttu-id="8705c-102">Предоставление пользователям размещенной голосовой почты в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8705c-102">Enable users for hosted voice mail in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8705c-103">_**Последнее изменение темы:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="8705c-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="8705c-104">Следуйте инструкциям по включению поддержки пользователями Lync Server 2013 для голосовой почты в размещенной службе единой системы обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="8705c-104">Follow the procedure to enable Lync Server 2013 users for voice mail on a hosted Exchange Unified Messaging (UM) service.</span></span>

<span data-ttu-id="8705c-105">Для получения дополнительных сведений см в документации по планированию [Hosted Management управление пользователями в Lync Server 2013](lync-server-2013-hosted-exchange-user-management.md) .</span><span class="sxs-lookup"><span data-stu-id="8705c-105">For details, see [Hosted Exchange user management in Lync Server 2013](lync-server-2013-hosted-exchange-user-management.md) in the Planning documentation.</span></span>

<span data-ttu-id="8705c-106">Подробные сведения о командлете [Set – CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) можно найти в документации по консоли управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8705c-106">For details about the [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) cmdlet, see the Lync Server Management Shell documentation.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="8705c-107">Прежде чем можно будет включить поддержку размещенной голосовой почты для пользователя Lync Server 2013, необходимо развернуть политику размещенной голосовой почты, которая применяется к учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="8705c-107">Before a Lync Server 2013 user can be enabled for hosted voice mail, a hosted voice mail policy that applies to their user account must be deployed.</span></span> <span data-ttu-id="8705c-108">Дополнительные сведения см. <A href="lync-server-2013-hosted-voice-mail-policies.md">в разделе политики размещенной голосовой почты в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="8705c-108">For details, see <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted voice mail policies in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-enable-users-for-hosted-voice-mail"></a><span data-ttu-id="8705c-109">To enable users for hosted voice mail</span><span class="sxs-lookup"><span data-stu-id="8705c-109">To enable users for hosted voice mail</span></span>

1.  <span data-ttu-id="8705c-110">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="8705c-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="8705c-p102">Выполните командлет Set-CsUser, чтобы настроить учетную запись пользователя для размещаемой голосовой почты. Например, выполните команду:</span><span class="sxs-lookup"><span data-stu-id="8705c-p102">Run the Set-CsUser cmdlet to configure the user account for hosted voice mail. For example, run:</span></span>
    
        Set-CsUser -HostedVoiceMail $True -Identity "contoso\kenmyer"
    
    <span data-ttu-id="8705c-113">Команда в предыдущем примере задает следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="8705c-113">The preceding example sets the following parameters:</span></span>
    
      - <span data-ttu-id="8705c-114">**HostedVoiceMail** включает маршрутизацию вызовов голосовой почты пользователей в размещаемую единую систему обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="8705c-114">**HostedVoiceMail** enables a user’s voice mail calls to be routed to hosted Exchange UM.</span></span> <span data-ttu-id="8705c-115">Он также сообщает Microsoft Lync 2013, чтобы получить индикатор "позвонить голосовой почте".</span><span class="sxs-lookup"><span data-stu-id="8705c-115">It also signals Microsoft Lync 2013 to light up the “call voice mail” indicator.</span></span>
    
      - <span data-ttu-id="8705c-p104">**Identity** ? указывает изменяемую учетную запись. Значение Identity можно указать, используя следующие форматы:</span><span class="sxs-lookup"><span data-stu-id="8705c-p104">**Identity** specifies the user account to be modified. The Identity value can be specified using any of the following formats:</span></span>
        
          - <span data-ttu-id="8705c-118">SIP-адрес пользователя;</span><span class="sxs-lookup"><span data-stu-id="8705c-118">The user's SIP address</span></span>
        
          - <span data-ttu-id="8705c-119">имя участника-пользователя Active Directory пользователя;</span><span class="sxs-lookup"><span data-stu-id="8705c-119">The user's Active Directory User-Principal-Name</span></span>
        
          - <span data-ttu-id="8705c-120">Имя для входа в\\домен пользователя (например, Contoso\\kenmyer).</span><span class="sxs-lookup"><span data-stu-id="8705c-120">The user's domain\\logon name (for example, contoso\\kenmyer)</span></span>
        
          - <span data-ttu-id="8705c-121">отображаемое имя доменных служб Active Directory пользователя (например, Ken Myer).</span><span class="sxs-lookup"><span data-stu-id="8705c-121">The user's Active Directory Domain Services Display-Name (for example, Ken Myer).</span></span> <span data-ttu-id="8705c-122">При использовании имени отображения в качестве значения идентификатора можно использовать подстановочный знак "звездочка"\*().</span><span class="sxs-lookup"><span data-stu-id="8705c-122">If using the Display-Name as the Identity value, you can use the asterisk (\*) wildcard character.</span></span> <span data-ttu-id="8705c-123">Например, идентификатор "\* Smith" возвращает всех пользователей с именем отображения, заканчивающимся строковым значением "Smith".</span><span class="sxs-lookup"><span data-stu-id="8705c-123">For example, the Identity "\* Smith" returns all the users who have a Display-Name that ends with the string value "Smith".</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="8705c-124">Имя-учетной-записи-SAM Active Directory пользователя нельзя использовать в качестве значения параметра Identity, так как это имя может быть неуникальным в лесу.</span><span class="sxs-lookup"><span data-stu-id="8705c-124">The user’s Active Directory SAM-Account-Name cannot be used as the Identity value because the SAM-Account-Name is not necessarily unique in the forest.</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

