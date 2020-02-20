---
title: 'Lync Server 2013: Добавление устройства для обеспечения связи в филиалах к Active Directory'
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
ms.openlocfilehash: fca31c97e0d059cda9f6b39a0e17e8350a37cf52
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145027"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="add-a-survivable-branch-appliance-to-active-directory-in-lync-server-2013"></a><span data-ttu-id="a8a43-102">Добавление устройства для обеспечения связи в филиалах в Active Directory в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a8a43-102">Add a Survivable Branch Appliance to Active Directory in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a8a43-103">_**Последнее изменение темы:** 2012-09-23_</span><span class="sxs-lookup"><span data-stu-id="a8a43-103">_**Topic Last Modified:** 2012-09-23_</span></span>

<span data-ttu-id="a8a43-104">Если вы планируете развернуть устройство для обеспечения связи в филиалах, необходимо добавить устройство для обеспечения связи в филиалах в доменные службы Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a8a43-104">If you plan to deploy a Survivable Branch Appliance, you must add the Survivable Branch Appliance to Active Directory Domain Services.</span></span> <span data-ttu-id="a8a43-105">Выполните эту процедуру на центральном сайте.</span><span class="sxs-lookup"><span data-stu-id="a8a43-105">Perform this procedure at the central site.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a8a43-106">Эту процедуру следует выполнять только при развертывании устройства для обеспечения связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="a8a43-106">Perform this procedure only if you are deploying a Survivable Branch Appliance.</span></span> <span data-ttu-id="a8a43-107">Не выполняйте его, если вы развертываете сервер для обеспечения связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="a8a43-107">Do not perform it if you are deploying a Survivable Branch Server.</span></span>



</div>

<div>

## <a name="to-add-an-survivable-branch-appliance-to-active-directory-domain-services"></a><span data-ttu-id="a8a43-108">Добавление устройства для обеспечения связи в филиалах в доменные службы Active Directory</span><span class="sxs-lookup"><span data-stu-id="a8a43-108">To add an Survivable Branch Appliance to Active Directory Domain Services</span></span>

1.  <span data-ttu-id="a8a43-109">Выполните вход на рядовой сервер в качестве члена группы «Администраторы предприятия».</span><span class="sxs-lookup"><span data-stu-id="a8a43-109">Log on to a member server as a member of the Enterprise Admins group.</span></span>

2.  <span data-ttu-id="a8a43-110">Нажмите кнопку **Пуск**, выберите **Администрирование** и затем **Пользователи и компьютеры Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="a8a43-110">Click **Start**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>

3.  <span data-ttu-id="a8a43-111">В меню **Действия** щелкните пункт **Создать** и затем **Компьютер**.</span><span class="sxs-lookup"><span data-stu-id="a8a43-111">On the **Actions** menu, click **New** and then click **Computer**.</span></span>

4.  <span data-ttu-id="a8a43-112">В диалоговом окне **новый объект-компьютер** введите имя объекта компьютера для устройства для обеспечения связи в филиале (например, BranchOffice1) и нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="a8a43-112">In the **New Object-Computer** dialog box, type in a name for the Survivable Branch Appliance computer object (for example, BranchOffice1), and then click **Change**.</span></span>

5.  <span data-ttu-id="a8a43-113">В диалоговом окне **Выбор: Пользователь или Группа** добавьте группу RTCUniversalSBATechnicians и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a8a43-113">In the **Select User or Group** dialog box, add the RTCUniversalSBATechnicians group and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a8a43-114">Позднее член группы RTCUniversalSBATechnicians на сайте филиала добавит это устройство в домен.</span><span class="sxs-lookup"><span data-stu-id="a8a43-114">A member of the RTCUniversalSBATechnicians group at the branch site will add this device to the domain later.</span></span>

    
    </div>

6.  <span data-ttu-id="a8a43-115">Нажмите кнопку **ОК** , чтобы сохранить объект компьютера устройства для обеспечения связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="a8a43-115">Click **OK** to save the Survivable Branch Appliance computer object.</span></span>

7.  <span data-ttu-id="a8a43-116">Нажмите кнопку **Пуск**, выберите **Администрирование** и затем **Редактирование ADSI**.</span><span class="sxs-lookup"><span data-stu-id="a8a43-116">Click **Start**, click **Administrative Tools**, and then click **ADSI Edit**.</span></span>

8.  <span data-ttu-id="a8a43-117">В окне **Редактирование ADSI** щелкните созданный ранее объект-компьютер правой кнопкой мыши и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="a8a43-117">In **ADSI Edit**, right-click the computer object that you created in the previous steps, and then click **Properties**.</span></span>

9.  <span data-ttu-id="a8a43-118">В списке атрибутов щелкните **servicePrincipalName** и нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="a8a43-118">In the attribute list, click **servicePrincipalName**, and then click **Edit**.</span></span>

10. <span data-ttu-id="a8a43-119">В поле **добавляемое значение** \<введите host/SBA\> FQDN, где \<полное\> доменное имя SBA — полное доменное имя устройства для обеспечения связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="a8a43-119">In the **Value to add** field, type HOST/\<SBA FQDN\> where \<SBA FQDN\> is the fully qualified domain name (FQDN) of your Survivable Branch Appliance.</span></span> <span data-ttu-id="a8a43-120">Например, введите **HOST/BranchOffice1.contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="a8a43-120">For example, type **HOST/BranchOffice1.contoso.com**.</span></span>

11. <span data-ttu-id="a8a43-121">Нажмите кнопку **ОК**, чтобы сохранить значение атрибута **servicePrincipalName**, а затем нажмите кнопку **ОК**, чтобы сохранить свойства объекта-компьютера.</span><span class="sxs-lookup"><span data-stu-id="a8a43-121">Click **OK** to save the **servicePrincipalName** attribute setting, and then click **OK** to save the computer object properties.</span></span>

12. <span data-ttu-id="a8a43-122">В окне **Пользователи и компьютеры Active Directory** щелкните правой кнопкой элемент **Пользователи**, выберите пункт **Создать** и щелкните элемент **Пользователь**.</span><span class="sxs-lookup"><span data-stu-id="a8a43-122">In **Active Directory Users and Computers**, right-click **Users**, click **New**, and then click **User**.</span></span>

13. <span data-ttu-id="a8a43-123">Введите данные в мастер, чтобы создать учетную запись пользователя домена для обеспечения связи с устройством для обеспечения связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="a8a43-123">Enter information into the wizard to create a domain user account for a Survivable Branch Appliance technician.</span></span>

14. <span data-ttu-id="a8a43-124">В окне **Пользователи и компьютеры Active Directory** щелкните элемент **Пользователи**, щелкните правой кнопкой объекта пользователя и выберите пункт **Добавить в группу**.</span><span class="sxs-lookup"><span data-stu-id="a8a43-124">In **Active Directory Users and Computers**, click **Users**, right-click the user object, and then click **Add to a group**.</span></span>

15. <span data-ttu-id="a8a43-125">В поле **Введите имена выбираемых объектов** введите **RTCUniversalSBATechnicians** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a8a43-125">In **Enter the object names to select**, type **RTCUniversalSBATechnicians**, and then click **OK**.</span></span>

16. <span data-ttu-id="a8a43-126">Повторите действия 12–15 для каждого техника филиала.</span><span class="sxs-lookup"><span data-stu-id="a8a43-126">Repeat Steps 12-15 for each branch site technician.</span></span>

<span data-ttu-id="a8a43-127">**Следующий шаг**: [Добавление сайтов филиалов в топологию в Lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md)</span><span class="sxs-lookup"><span data-stu-id="a8a43-127">**Next step**: [Add branch sites to your topology in Lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

