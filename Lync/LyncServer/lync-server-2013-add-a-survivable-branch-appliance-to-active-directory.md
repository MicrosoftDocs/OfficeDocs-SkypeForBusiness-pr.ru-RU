---
title: 'Lync Server 2013: добавление устройства для обеспечения связи в филиалах к Active Directory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add a Survivable Branch Appliance to Active Directory
ms:assetid: 3e63507c-d60b-40ec-8bbe-586b1d707c3e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425906(v=OCS.15)
ms:contentKeyID: 48183938
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8712dcb5b68522a8b770aac63c5a37a1a70a669a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735069"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-a-survivable-branch-appliance-to-active-directory-in-lync-server-2013"></a><span data-ttu-id="e6a31-102">Добавление устройства для обеспечения связи в филиалах к Active Directory в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e6a31-102">Add a Survivable Branch Appliance to Active Directory in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e6a31-103">_**Тема последнего изменения:** 2012-09-23_</span><span class="sxs-lookup"><span data-stu-id="e6a31-103">_**Topic Last Modified:** 2012-09-23_</span></span>

<span data-ttu-id="e6a31-104">Если вы планируете развертывать бесперебойно работающее устройство филиалов, необходимо добавить его бесперебойную ветвь в доменные службы Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e6a31-104">If you plan to deploy a Survivable Branch Appliance, you must add the Survivable Branch Appliance to Active Directory Domain Services.</span></span> <span data-ttu-id="e6a31-105">Выполните эту процедуру на центральном веб-сайте.</span><span class="sxs-lookup"><span data-stu-id="e6a31-105">Perform this procedure at the central site.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e6a31-106">Выполните эту процедуру только в том случае, если вы развертываете бесперебойную ветвь устройства.</span><span class="sxs-lookup"><span data-stu-id="e6a31-106">Perform this procedure only if you are deploying a Survivable Branch Appliance.</span></span> <span data-ttu-id="e6a31-107">Не выполняйте его, если вы развертываете бесперебойный сервер филиала.</span><span class="sxs-lookup"><span data-stu-id="e6a31-107">Do not perform it if you are deploying a Survivable Branch Server.</span></span>



</div>

<div>

## <a name="to-add-an-survivable-branch-appliance-to-active-directory-domain-services"></a><span data-ttu-id="e6a31-108">Добавление бесперебойно работающего устройства филиалов в доменные службы Active Directory</span><span class="sxs-lookup"><span data-stu-id="e6a31-108">To add an Survivable Branch Appliance to Active Directory Domain Services</span></span>

1.  <span data-ttu-id="e6a31-109">Войдите в систему на рядовом сервере, который входит в группу администраторов предприятия.</span><span class="sxs-lookup"><span data-stu-id="e6a31-109">Log on to a member server as a member of the Enterprise Admins group.</span></span>

2.  <span data-ttu-id="e6a31-110">Нажмите кнопку **Пуск**и выберите пункт **Администрирование**, а затем — **Пользователи и компьютеры Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="e6a31-110">Click **Start**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>

3.  <span data-ttu-id="e6a31-111">В меню **действия** выберите команду **создать** , а затем — пункт **компьютер**.</span><span class="sxs-lookup"><span data-stu-id="e6a31-111">On the **Actions** menu, click **New** and then click **Computer**.</span></span>

4.  <span data-ttu-id="e6a31-112">В диалоговом окне **новый объект-компьютер** введите имя для объекта компьютера, работающего с устройством филиала (например, BranchOffice1), и нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="e6a31-112">In the **New Object-Computer** dialog box, type in a name for the Survivable Branch Appliance computer object (for example, BranchOffice1), and then click **Change**.</span></span>

5.  <span data-ttu-id="e6a31-113">В диалоговом окне **Выбор пользователя или группы** добавьте группу рткуниверсалсбатечниЦианс и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e6a31-113">In the **Select User or Group** dialog box, add the RTCUniversalSBATechnicians group and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e6a31-114">Участник группы РткуниверсалсбатечниЦианс на сайте филиала добавит это устройство в домен позже.</span><span class="sxs-lookup"><span data-stu-id="e6a31-114">A member of the RTCUniversalSBATechnicians group at the branch site will add this device to the domain later.</span></span>

    
    </div>

6.  <span data-ttu-id="e6a31-115">Нажмите кнопку **ОК** , чтобы сохранить объект управляемого устройства управления филиалом.</span><span class="sxs-lookup"><span data-stu-id="e6a31-115">Click **OK** to save the Survivable Branch Appliance computer object.</span></span>

7.  <span data-ttu-id="e6a31-116">Нажмите кнопку **Пуск**и выберите пункт **Администрирование**, а затем — пункт **ADSI Edit**.</span><span class="sxs-lookup"><span data-stu-id="e6a31-116">Click **Start**, click **Administrative Tools**, and then click **ADSI Edit**.</span></span>

8.  <span data-ttu-id="e6a31-117">В окне " **Редактирование ADSI**" щелкните правой кнопкой мыши объект компьютера, созданный на предыдущих этапах, и выберите пункт **свойства**.</span><span class="sxs-lookup"><span data-stu-id="e6a31-117">In **ADSI Edit**, right-click the computer object that you created in the previous steps, and then click **Properties**.</span></span>

9.  <span data-ttu-id="e6a31-118">В списке атрибутов выберите значение " **/",** а затем нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="e6a31-118">In the attribute list, click **servicePrincipalName**, and then click **Edit**.</span></span>

10. <span data-ttu-id="e6a31-119">В поле **значение для добавления** \<введите host/СБА\> FQDN, где \<СБА FQDN\> — полное доменное имя (FQDN) работающего устройства филиала.</span><span class="sxs-lookup"><span data-stu-id="e6a31-119">In the **Value to add** field, type HOST/\<SBA FQDN\> where \<SBA FQDN\> is the fully qualified domain name (FQDN) of your Survivable Branch Appliance.</span></span> <span data-ttu-id="e6a31-120">Например, введите **Host/BranchOffice1. contoso. com**.</span><span class="sxs-lookup"><span data-stu-id="e6a31-120">For example, type **HOST/BranchOffice1.contoso.com**.</span></span>

11. <span data-ttu-id="e6a31-121">Нажмите кнопку **ОК** , чтобы сохранить **значение атрибута,** и нажмите кнопку **ОК** , чтобы сохранить свойства объекта компьютера.</span><span class="sxs-lookup"><span data-stu-id="e6a31-121">Click **OK** to save the **servicePrincipalName** attribute setting, and then click **OK** to save the computer object properties.</span></span>

12. <span data-ttu-id="e6a31-122">В окне " **Пользователи и компьютеры Active Directory**" щелкните правой кнопкой мыши пункт **Пользователи**, выберите команду **создать**, а затем — пункт **пользователь**.</span><span class="sxs-lookup"><span data-stu-id="e6a31-122">In **Active Directory Users and Computers**, right-click **Users**, click **New**, and then click **User**.</span></span>

13. <span data-ttu-id="e6a31-123">Введите данные в мастер, чтобы создать учетную запись пользователя домена для работающего техника управляющего устройства ветвления.</span><span class="sxs-lookup"><span data-stu-id="e6a31-123">Enter information into the wizard to create a domain user account for a Survivable Branch Appliance technician.</span></span>

14. <span data-ttu-id="e6a31-124">В окне **Пользователи и компьютеры Active Directory**выберите пункт **Пользователи**, щелкните правой кнопкой мыши объект пользователя и выберите команду **Добавить в группу**.</span><span class="sxs-lookup"><span data-stu-id="e6a31-124">In **Active Directory Users and Computers**, click **Users**, right-click the user object, and then click **Add to a group**.</span></span>

15. <span data-ttu-id="e6a31-125">В поле **Введите имена объектов для выбора**введите **рткуниверсалсбатечниЦианс**и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e6a31-125">In **Enter the object names to select**, type **RTCUniversalSBATechnicians**, and then click **OK**.</span></span>

16. <span data-ttu-id="e6a31-126">Повторите шаги 12-15 для каждого техника сайта подразделения.</span><span class="sxs-lookup"><span data-stu-id="e6a31-126">Repeat Steps 12-15 for each branch site technician.</span></span>

<span data-ttu-id="e6a31-127">**Следующий шаг**: [Добавление сайтов филиалов в топологию в Lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md)</span><span class="sxs-lookup"><span data-stu-id="e6a31-127">**Next step**: [Add branch sites to your topology in Lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

