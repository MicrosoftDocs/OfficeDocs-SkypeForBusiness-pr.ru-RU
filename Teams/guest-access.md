---
title: "Управление гостевым доступом в Microsoft Teams"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Гостевой доступ в Microsoft Teams позволяет командам в вашей организации сотрудничать с людьми, находящимися за пределами организации, предоставляя им доступ к командам и каналам."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: f440e1d67166931365a24cb18e855a179fc532ef
ms.sourcegitcommit: 34abc255257716ab135e8eda7b07f8abb55a6bc7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/02/2017
---
<a name="manage-guest-access-in-microsoft-teams"></a><span data-ttu-id="85231-103">Управление гостевым доступом в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="85231-103">Manage guest access in Microsoft Teams</span></span>
======================================


<span data-ttu-id="85231-104">Гостевой доступ в Microsoft Teams позволяет командам в вашей организации сотрудничать с людьми, находящимися за пределами организации, предоставляя им доступ к командам и каналам.</span><span class="sxs-lookup"><span data-stu-id="85231-104">Guest access in Microsoft Teams allows teams in your organization to collaborate with people outside your organization by granting them access to teams and channels.</span></span> <span data-ttu-id="85231-105">Гость — это человек, не являющийся сотрудником, учащимся или участником вашей организации.</span><span class="sxs-lookup"><span data-stu-id="85231-105">A guest is someone who isn't an employee, student, or member of your organization.</span></span> <span data-ttu-id="85231-106">У него нет учебной или рабочей учетной записи в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="85231-106">They don't have a school or work account with your organization.</span></span> <span data-ttu-id="85231-107">Например, к гостям могут относиться партнеры, продавцы, поставщики или консультанты.</span><span class="sxs-lookup"><span data-stu-id="85231-107">For example, guests may include partners, vendors, suppliers, or consultants.</span></span>
  
    
    

<span data-ttu-id="85231-108">Организации, использующие Teams, могут предоставлять своим партнерам внешний доступ к командам, документам в каналах, ресурсам, чатам и приложениям, при этом сохраняя полный контроль над своими корпоративными данными.</span><span class="sxs-lookup"><span data-stu-id="85231-108">Organizations using Teams can provide external access to teams, documents in channels, resources, chats, and applications to their partners, while maintaining complete control over their own corporate data.</span></span>

<span data-ttu-id="85231-109">Продукт Teams основан на Группах Office 365 и предоставляет новый способ доступа к общим активам для группы Office 365.</span><span class="sxs-lookup"><span data-stu-id="85231-109">Teams is built upon Office 365 Groups and provides a new way to access shared assets for an Office 365 group.</span></span> <span data-ttu-id="85231-110">Teams является оптимальным решением для сохраняемого чата между участниками группы или команды.</span><span class="sxs-lookup"><span data-stu-id="85231-110">Teams is the best solution for persistent chat among group/team members.</span></span> <span data-ttu-id="85231-111">Группы Office 365 — это служба, предоставляющая членство на несколько приложений для набора общих активов команды, таких как сайт SharePoint или панель мониторинга Power BI, чтобы обеспечить эффективную и безопасную работу команды.</span><span class="sxs-lookup"><span data-stu-id="85231-111">Office 365 Groups is a service that provides cross-application membership for a set of shared team assets, like a SharePoint site or a Power BI dashboard, so that the team can collaborate effectively and securely.</span></span>
  
    
    

## <a name="how-a-guest-joins-a-team"></a><span data-ttu-id="85231-112">Присоединение гостя к команде</span><span class="sxs-lookup"><span data-stu-id="85231-112">How a guest joins a team</span></span>


  
    
    
<span data-ttu-id="85231-113">Владелец команды в Teams может добавлять гостей в свои команды и управлять ими через классический или веб-клиент.</span><span class="sxs-lookup"><span data-stu-id="85231-113">A team owner in Teams can add and manage guests in their teams via the web or desktop.</span></span> <span data-ttu-id="85231-114">В качестве гостей можно добавить только пользователей с адресом электронной почты, соответствующим рабочей или учебной учетной записи Office 365 или Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="85231-114">Only users who have an email address corresponding to an Azure Active Directory or Office 365 work or school account can be added as a guest user.</span></span>
  
    
    

> [!NOTE]
> <span data-ttu-id="85231-115">Прежде чем гости смогут присоединиться к команде, администратору нужно включить в Teams гостевой доступ.</span><span class="sxs-lookup"><span data-stu-id="85231-115">Before guests can join a team, an admin must enable guest access in Teams.</span></span> <span data-ttu-id="85231-116">Для этого [войдите в систему](https://portal.office.com/adminportal/home) с использованием учетной записи глобального администратора Office 365.</span><span class="sxs-lookup"><span data-stu-id="85231-116">To do that,  [sign in](https://portal.office.com/adminportal/home) with your Office 365 global admin account.</span></span> <span data-ttu-id="85231-117">Затем выберите **Параметры** > **Services &amp; add-ins** (Службы и надстройки) > **Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="85231-117">Then, choose **Settings** > **Services &amp; add-ins** > **Microsoft Teams**.</span></span> <span data-ttu-id="85231-118">Выберите **Гость** в поле **Select the user/license type you want to configure** (Выберите тип пользователя или лицензии для настройки), а затем выберите **Включить** в поле **Turn Microsoft Teams on or off for all users of this type** (Включить или отключить Microsoft Teams для всех пользователей этого типа).</span><span class="sxs-lookup"><span data-stu-id="85231-118">Select **Guest** in **Select the user/license type you want to configure**, and select **On** in **Turn Microsoft Teams on or off for all users of this type**.</span></span> <span data-ttu-id="85231-119">Применение параметров может занять до одного часа.</span><span class="sxs-lookup"><span data-stu-id="85231-119">It can take up to an hour for the settings to take effect.</span></span> <span data-ttu-id="85231-120">Дополнительные сведения см. в разделе "Включение и отключение гостевого доступа для Microsoft Teams" на вкладке "Управление" этой статьи.</span><span class="sxs-lookup"><span data-stu-id="85231-120">For more details, see "Turn on or off guest access for Microsoft Teams" on this article's Manage tab.</span></span> 
  
    
    

<span data-ttu-id="85231-121">Ниже описано, как гость может стать участником команды:</span><span class="sxs-lookup"><span data-stu-id="85231-121">Here's how a guest becomes a member of a team:</span></span>
  
    
    

- <span data-ttu-id="85231-122">**Шаг 1.** Владелец команды или администратор Office 365 [добавляет гостя в команду](https://support.office.com/en-us/article/adds-a-guest-to-a-team-df38ae23-8f85-46d3-b071-cb11b9de5499#bkmk_addingguests).</span><span class="sxs-lookup"><span data-stu-id="85231-122">**Step 1** A team owner or an Office 365 admin [adds a guest to a team](https://support.office.com/en-us/article/adds-a-guest-to-a-team-df38ae23-8f85-46d3-b071-cb11b9de5499#bkmk_addingguests).</span></span>
    
  
- <span data-ttu-id="85231-123">**Шаг 2.** При необходимости администратор Office 365 или владелец команды может управлять доступными гостю возможностями.</span><span class="sxs-lookup"><span data-stu-id="85231-123">**Step 2** The Office 365 admin or the team owner can manage a guest's capabilities as necessary.</span></span> <span data-ttu-id="85231-124">Например, он может разрешить гостю добавлять или удалять каналы либо запретить ему доступ к файлам.</span><span class="sxs-lookup"><span data-stu-id="85231-124">For example, allowing a guest to add or delete channels or disabling access to files.</span></span>
    
  
- <span data-ttu-id="85231-125">**Шаг 3.** Гость получает от владельца команды приветственное сообщение электронной почты с приглашением присоединиться к команде.</span><span class="sxs-lookup"><span data-stu-id="85231-125">**Step 3** The guest receives a welcome email from the team owner, inviting them to join the team.</span></span> <span data-ttu-id="85231-126">Приняв приглашение, гость может [участвовать в деятельности команд и каналов](https://support.office.com/en-us/article/participate-in-teams-and-channels-df38ae23-8f85-46d3-b071-cb11b9de5499#bkmk_channels), получать сообщения каналов и отвечать на них, [обращаться к файлам в каналах](https://support.office.com/en-us/article/access-files-in-channels-c593c78a-27c4-4661-a598-682baa30ca7e), а также общаться в чате.</span><span class="sxs-lookup"><span data-stu-id="85231-126">After accepting the invitation, the guest can [participate in teams and channels](https://support.office.com/en-us/article/participate-in-teams-and-channels-df38ae23-8f85-46d3-b071-cb11b9de5499#bkmk_channels), receive and respond to channel messages, [access files in channels](https://support.office.com/en-us/article/access-files-in-channels-c593c78a-27c4-4661-a598-682baa30ca7e), and participate in chat.</span></span> <span data-ttu-id="85231-127">Во время работы с Teams участники команды явно уведомляются о наличии в команде гостя с помощью текстовых сообщений и значков.</span><span class="sxs-lookup"><span data-stu-id="85231-127">While using Teams, a combination of text and icons gives all team members clear indication of guest participation in a team.</span></span> <span data-ttu-id="85231-128">Дополнительные сведения см. в разделе [Взаимодействие с гостями](#guestexp)</span><span class="sxs-lookup"><span data-stu-id="85231-128">For more details, see [what the guest experience is like](#guestexp)</span></span>
    
  
<span data-ttu-id="85231-129">Гости могут в любое время покинуть команду с помощью классического или веб-клиента Teams.</span><span class="sxs-lookup"><span data-stu-id="85231-129">Guests can leave the team at any time via Teams web and desktop clients.</span></span> <span data-ttu-id="85231-130">Дополнительные сведения см. в разделе [Как покинуть команду?](https://support.office.com/en-us/article/How-do-I-leave-a-team-df38ae23-8f85-46d3-b071-cb11b9de5499#bkmk_howdoileaveateam)</span><span class="sxs-lookup"><span data-stu-id="85231-130">For details, see  [How do I leave a team?](https://support.office.com/en-us/article/How-do-I-leave-a-team-df38ae23-8f85-46d3-b071-cb11b9de5499#bkmk_howdoileaveateam)</span></span>
  
    
    

> [!NOTE]
> <span data-ttu-id="85231-131">В качестве гостей можно добавлять только людей, находящихся за пределами вашей организации, например партнеров или консультантов.</span><span class="sxs-lookup"><span data-stu-id="85231-131">Only people who are outside of your organization, such as partners or consultants, can be added as guests.</span></span> <span data-ttu-id="85231-132">Сотрудники вашей организации могут присоединяться в качестве обычных участников команды.</span><span class="sxs-lookup"><span data-stu-id="85231-132">People from within your organization can join as regular team members.</span></span> 
  
    
    

<a name="guestexp"></a>
## <a name="what-the-guest-experience-is-like"></a><span data-ttu-id="85231-133">Взаимодействие с гостями</span><span class="sxs-lookup"><span data-stu-id="85231-133">What the guest experience is like</span></span>

<span data-ttu-id="85231-134">Когда гостя приглашают присоединиться к команде, он получает приветственное сообщение электронной почты, содержащее некоторые сведения о команде и приобретаемых возможностях.</span><span class="sxs-lookup"><span data-stu-id="85231-134">When a guest is invited to join a team, they receive a welcome email message that includes some information about the team and what to expect now that they're a member.</span></span> <span data-ttu-id="85231-135">Прежде чем получить доступ к команде и ее каналам, гость должен активировать приглашение в сообщении.</span><span class="sxs-lookup"><span data-stu-id="85231-135">The guest must redeem the invitation in the email message before they can access the team and its channels.</span></span>
  
    
    

  
    
    
![На снимке экрана показан пример приветственного сообщения, отправленного гостевому пользователю владельцем команды в Microsoft Teams.](media/bc0deb82-6394-4280-8fed-312645c8fefe.png)
  
    
    
<span data-ttu-id="85231-138">Все участники команды видят в беседе канала сообщение о том, что владелец добавил гостя с определенным именем.</span><span class="sxs-lookup"><span data-stu-id="85231-138">All team members see a message in the channel thread announcing that the team owner has added a guest and providing the guest's name.</span></span> <span data-ttu-id="85231-139">Любой участник команды может легко определить, кто именно является гостем.</span><span class="sxs-lookup"><span data-stu-id="85231-139">Everyone on the team can identify easily who is a guest.</span></span> <span data-ttu-id="85231-140">На следующем снимке экрана для примера команды отображается баннер с текстом "В состав этой группы входят гости", а рядом с именем каждого гостя находится метка "Гость".</span><span class="sxs-lookup"><span data-stu-id="85231-140">As shown in the following screenshot of a sample team, a banner indicates "This team has guests" and a "GUEST" label appears next to each guest's name.</span></span>
  
    
    

  
    
    
![Снимок экрана показывает часть канала "Маркетинг" для компании Northwind Traders, где в верхней части экрана отображается баннер "В состав этой группы входят гости", а рядом с именами гостей стоит слово "Гость".](media/33394a31-7d10-4950-8b39-b7d9953397c3.png)
  
    
    
<span data-ttu-id="85231-142">В следующей таблице сравниваются функции Microsoft Teams, доступные участникам команды в организации и гостевому пользователю этой команды.</span><span class="sxs-lookup"><span data-stu-id="85231-142">The following table compares the Microsoft Teams functionality available for an organization's team members to the functionality available for a guest user on the team.</span></span>
  
    
    


|<span data-ttu-id="85231-143">**Возможности в Teams**</span><span class="sxs-lookup"><span data-stu-id="85231-143">**Capability in Teams**</span></span>|<span data-ttu-id="85231-144">**Пользователь Teams в организации**</span><span class="sxs-lookup"><span data-stu-id="85231-144">**Teams user in the organization**</span></span>|<span data-ttu-id="85231-145">**Гостевой пользователь**</span><span class="sxs-lookup"><span data-stu-id="85231-145">**Guest user**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="85231-146">Создание канала</span><span class="sxs-lookup"><span data-stu-id="85231-146">Create a channel</span></span>  <br/>  <span data-ttu-id="85231-147">*Этим параметром управляет владелец команды.*</span><span class="sxs-lookup"><span data-stu-id="85231-147">*Team owners control this setting.*</span></span>  <br/> |![Галочка](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)|![Галочка](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)|
|<span data-ttu-id="85231-150">Участие в приватном чате</span><span class="sxs-lookup"><span data-stu-id="85231-150">Participate in a private chat</span></span>  <br/> |![Галочка](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)|![Галочка](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)|
|<span data-ttu-id="85231-153">Участие в беседе канала</span><span class="sxs-lookup"><span data-stu-id="85231-153">Participate in a channel conversation</span></span>  <br/> |![Галочка](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)|![Галочка](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)|
|<span data-ttu-id="85231-156">Публикация, удаление и изменение сообщений</span><span class="sxs-lookup"><span data-stu-id="85231-156">Post, delete, and edit messages</span></span>  <br/> |![Галочка](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)|![Галочка](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)|
|<span data-ttu-id="85231-159">Общий доступ к файлу в канале</span><span class="sxs-lookup"><span data-stu-id="85231-159">Share a channel file</span></span>  <br/> |![Галочка](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)|![Галочка](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)|
|<span data-ttu-id="85231-162">Общий доступ к файлу в чате</span><span class="sxs-lookup"><span data-stu-id="85231-162">Share a chat file</span></span>  <br/> |![Галочка](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)||
|<span data-ttu-id="85231-164">Добавление приложений (вкладок, ботов или соединителей)</span><span class="sxs-lookup"><span data-stu-id="85231-164">Add apps (tabs, bots, or connectors)</span></span>  <br/> |![Галочка](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)||
|<span data-ttu-id="85231-166">Создание политик гостевого доступа, действующих как на уровне клиента, так и для отдельных команд или каналов</span><span class="sxs-lookup"><span data-stu-id="85231-166">Create tenant-wide and teams/channels guest access policies</span></span>  <br/> |![Галочка](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)||
|<span data-ttu-id="85231-168">Приглашение пользователя извне домена клиента Office 365</span><span class="sxs-lookup"><span data-stu-id="85231-168">Invite a user outside the Office 365 tenant's domain</span></span>  <br/> ||![Галочка](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)|
|<span data-ttu-id="85231-170">Создание команды</span><span class="sxs-lookup"><span data-stu-id="85231-170">Create a team</span></span>  <br/> |![Галочка](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)||
|<span data-ttu-id="85231-172">Обнаружение и присоединение открытой команды</span><span class="sxs-lookup"><span data-stu-id="85231-172">Discover and join a public team</span></span>  <br/> |![Галочка](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)||
|<span data-ttu-id="85231-174">Просмотр организационной диаграммы</span><span class="sxs-lookup"><span data-stu-id="85231-174">View organization chart</span></span>  <br/> |![Галочка](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)||
   

    
> [!NOTE]
> <span data-ttu-id="85231-176">Администраторы Office 365 управляют доступными гостям функциями.</span><span class="sxs-lookup"><span data-stu-id="85231-176">Office 365 admins control the features available to guests.</span></span> 
  
    
## <a name="manage-guests"></a><span data-ttu-id="85231-177">Управление гостями</span><span class="sxs-lookup"><span data-stu-id="85231-177">Manage guests</span></span>


<span data-ttu-id="85231-178">Функция гостевого доступа включена во все подписки Office 365 бизнес премиум, Office 365 корпоративный и Office 365 для образования.</span><span class="sxs-lookup"><span data-stu-id="85231-178">Guest access is included with all Office 365 Business Premium, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="85231-179">Дополнительная лицензия Office 365 не требуется.</span><span class="sxs-lookup"><span data-stu-id="85231-179">No additional Office 365 license is necessary.</span></span>
  
    
    
<span data-ttu-id="85231-180">Функция гостевого доступа Teams действует на уровне клиента и по умолчанию отключена.</span><span class="sxs-lookup"><span data-stu-id="85231-180">Teams guest access is a tenant-level setting and is turned off by default.</span></span> <span data-ttu-id="85231-181">Администраторы могут управлять ею с помощью Центра администрирования Office 365.</span><span class="sxs-lookup"><span data-stu-id="85231-181">Admins can manage guest access via the Office 365 admin center.</span></span> <span data-ttu-id="85231-182">Дополнительные сведения см. в разделах [Управление гостевым доступом в Microsoft Teams](#manageguest) и [Контроль гостевого доступа в Microsoft Teams](#controlguest).</span><span class="sxs-lookup"><span data-stu-id="85231-182">For more details, see [Manage guest access to Microsoft Teams](#manageguest) and [Control guest access to Microsoft Teams](#controlguest).</span></span>
  
    
    

> [!NOTE]
> <span data-ttu-id="85231-183">Параметр клиента для гостевого доступа Teams запрещает только вход гостей.</span><span class="sxs-lookup"><span data-stu-id="85231-183">The Teams guest access tenant setting only prevents guest sign-in.</span></span> <span data-ttu-id="85231-184">Владельцы смогут приглашать в свои команды новых гостей и гостей из существующих каталогов.</span><span class="sxs-lookup"><span data-stu-id="85231-184">Team owners will be able to invite new guests and add existing directory guest users to their respective teams.</span></span> <span data-ttu-id="85231-185">Следует напомнить, что продукт Teams всегда учитывает внешние параметры Azure Active Directory при разрешении или запрете добавления гостя в клиент.</span><span class="sxs-lookup"><span data-stu-id="85231-185">As a reminder, Teams always honors Azure Active Directory external settings to allow or prevent guest user addition to the tenant.</span></span> 
  
    
    

<span data-ttu-id="85231-186">Кроме того, для управления гостями и их доступом к ресурсам Office 365 и Teams вы можете использовать портал Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="85231-186">In addition, you can use the Azure Active Directory portal to manage guests and their access to Office 365 and Teams resources.</span></span> <span data-ttu-id="85231-187">Функция гостевого доступа использует возможности службы совместной работы бизнес-бизнес (B2B) Azure Active Directory в качестве базовой инфраструктуры, чтобы хранить, например, свойства удостоверений, сведения о членстве и параметры многофакторной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="85231-187">Teams guest access makes use of Azure Active Directory business-to-business (B2B) collaboration capabilities as the underlying infrastructure to store security principles information such as identity properties, memberships, and multi-factor authentication settings.</span></span> <span data-ttu-id="85231-188">Дополнительные сведения об Azure Active Directory B2B см. в статьях [Что такое служба совместной работы Azure AD B2B?](https://go.microsoft.com/fwlink/p/?linkid=853011) и [Вопросы и ответы по службе совместной работы Azure Active Directory B2B](https://go.microsoft.com/fwlink/p/?linkid=853020).</span><span class="sxs-lookup"><span data-stu-id="85231-188">To learn more about Azure Active Directory B2B, see [What is Azure AD B2B collaboration?](https://go.microsoft.com/fwlink/p/?linkid=853011) and [Azure Active Directory B2B collaboration FAQs](https://go.microsoft.com/fwlink/p/?linkid=853020).</span></span>
  
    
    

#### <a name="related-key-services-and-dependencies"></a><span data-ttu-id="85231-189">Ключевые связанные службы и зависимости</span><span class="sxs-lookup"><span data-stu-id="85231-189">Related key services and dependencies</span></span>

<span data-ttu-id="85231-190">Система Teams использует SharePoint Online и OneDrive для бизнеса, чтобы хранить файлы и документы для бесед в каналах и чате.</span><span class="sxs-lookup"><span data-stu-id="85231-190">Teams relies on SharePoint Online and OneDrive for Business to store files and documents for channels and chat conversations.</span></span> <span data-ttu-id="85231-191">Кроме того, Teams использует Группы Office 365 для хранения сведений о членстве в командах и других свойств, например параметров классификации данных для команд.</span><span class="sxs-lookup"><span data-stu-id="85231-191">In addition, Teams relies on Office 365 groups to store teams' memberships and other properties such as team data classification settings.</span></span>
  
    
    
<span data-ttu-id="85231-192">Чтобы обеспечить полноценный гостевой доступ в Teams, администраторам Office 365 следует выбрать значение **Включить** для следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="85231-192">To enable the full Teams guest access experience, Office 365 admins need to select **On** for the following settings:</span></span>
  
    
    

- <span data-ttu-id="85231-193">В SharePoint Online: **Only allow sharing with external users already in the directory (Разрешить общий доступ только с внешними пользователями, уже присутствующими в каталоге)**</span><span class="sxs-lookup"><span data-stu-id="85231-193">In SharePoint Online: **Only allow sharing with external users already in the directory**</span></span>
    
    <span data-ttu-id="85231-194">Дополнительные сведения см. в статье [Управление внешним общим доступом для среды SharePoint Online](https://support.office.com/en-us/article/Manage-external-sharing-for-your-SharePoint-Online-environment-c8a462eb-0723-4b0b-8d0a-70feafe4be85).</span><span class="sxs-lookup"><span data-stu-id="85231-194">For more information, see [Manage external sharing for your SharePoint Online environment](https://support.office.com/en-us/article/Manage-external-sharing-for-your-SharePoint-Online-environment-c8a462eb-0723-4b0b-8d0a-70feafe4be85).</span></span>
    
  
- <span data-ttu-id="85231-195">В Группах Office 365: **Let group owners add people outside the organization to groups (Разрешить владельцам добавлять в группы людей извне организации)**</span><span class="sxs-lookup"><span data-stu-id="85231-195">In Office 365 groups: **Let group owners add people outside the organization to groups**</span></span>
    
    <span data-ttu-id="85231-196">Дополнительные сведения см. в статье [Контроль гостевого доступа в Microsoft Teams](#controlguest).</span><span class="sxs-lookup"><span data-stu-id="85231-196">For more information, see [Control guest access to Microsoft Teams](#controlguest).</span></span>
    
  

#### <a name="turn-on-or-off-guest-access-for-microsoft-teams"></a><span data-ttu-id="85231-197">Включение и отключение гостевого доступа для Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="85231-197">Turn on or off guest access for Microsoft Teams</span></span>
<span data-ttu-id="85231-198"><a name="bkmk_TurnonOrTurnOff"> </a></span><span class="sxs-lookup"><span data-stu-id="85231-198"></span></span>


1. <span data-ttu-id="85231-199">Войдите с использованием учетной записи глобального администратора Office 365 по адресу [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span><span class="sxs-lookup"><span data-stu-id="85231-199">Sign in with your Office 365 global admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
  
2. <span data-ttu-id="85231-200">В меню навигации выберите **Параметры** и затем **Services &amp; add-ins** (Службы и надстройки).</span><span class="sxs-lookup"><span data-stu-id="85231-200">In the navigation menu, choose **Settings** and then select **Services &amp; add-ins**.</span></span>
    
     ![Войдите в Office 365, перейдите в Центр администрирования Office 365, выберите "Параметры" и затем "Services &amp; add-ins" (Службы и надстройки).](media/99e676d4-5b48-4525-9556-547031fa37d9.png)
  
 

  
3. <span data-ttu-id="85231-202">Выберите **Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="85231-202">Select **Microsoft Teams**.</span></span>
    
     ![Снимок экрана, показывающий параметр для надстройки Microsoft Teams, выбранный в Центре администрирования Office 365.](media/17ac5608-d212-4fa8-ae3a-e78c62003968.png)
  
  
4. <span data-ttu-id="85231-204">В поле **Select the user/license type you want to configure** (Выберите тип пользователя или лицензии для настройки) укажите параметр **Гость**.</span><span class="sxs-lookup"><span data-stu-id="85231-204">In **Select the user/license type you want to configure**, select **Guest**.</span></span>
    
  
![Снимок экрана надстройки Microsoft Teams, показывающий выбранную лицензию "Гость" и значение "Включить" для параметра Microsoft Teams.](media/92aabda5-431c-4fdd-803e-5ab49290f4f7.png)
  
  
5. <span data-ttu-id="85231-206">Выберите значение **Включить** для параметра **Turn Microsoft Teams on or off for all users of this type** (Включить или отключить Microsoft Teams для всех пользователей этого типа), чтобы включить Teams и гостевой доступ в организации, а затем выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="85231-206">Click or tap the toggle next to **Turn Microsoft Teams on or off for all users of this type** to **On** to turn on Teams and guest access for your organization, and then choose **Save**.</span></span> 
    
  
> [!NOTE]
> <span data-ttu-id="85231-207">Применение параметров может занять до одного часа.</span><span class="sxs-lookup"><span data-stu-id="85231-207">It can take up to an hour for the settings to take effect.</span></span> 
  
    
## <a name="control-adding-guest-users-to-microsoft-teams-and-office-365-groups"></a><span data-ttu-id="85231-208">Управление добавлением гостевых пользователей в Microsoft Teams и Группы Office 365</span><span class="sxs-lookup"><span data-stu-id="85231-208">Control adding guest users to Microsoft Teams and Office 365 Groups</span></span>
<span data-ttu-id="85231-209"><a name="bkmk_ControlAddingGuestUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="85231-209"></span></span>


1. <span data-ttu-id="85231-210">Войдите с использованием учетной записи глобального администратора Office 365 по адресу [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span><span class="sxs-lookup"><span data-stu-id="85231-210">Sign in with your Office 365 global admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
  
2. <span data-ttu-id="85231-211">В меню навигации выберите **Параметры** и затем **Services &amp; add-ins** (Службы и надстройки).</span><span class="sxs-lookup"><span data-stu-id="85231-211">In the navigation menu, choose **Settings** and then select **Services &amp; add-ins**.</span></span>
    
  
3. <span data-ttu-id="85231-212">Выберите **Группы Office 365**.</span><span class="sxs-lookup"><span data-stu-id="85231-212">Select **Office 365 Groups**.</span></span>
    
     ![Группы Office 365](media/e25a7920-254c-4da3-bc5f-a8c7f6b61423.png)
  

  

  
4. <span data-ttu-id="85231-214">На странице "Группы Office 365" установите переключатель в положение **Включить** или **Отключить**, в зависимости от того, хотите ли вы разрешить владельцам групп доступ к группам Office 365 извне организации.</span><span class="sxs-lookup"><span data-stu-id="85231-214">On the Office 365 Groups page, set the toggle to **On** or **Off**, depending if you want to let team and group owners outside your organization access Office 365 groups.</span></span> <span data-ttu-id="85231-215">Выберите значение **Включить** рядом с параметром **Let group owners add people outside the organization to groups** (Разрешить владельцам добавлять в группы людей извне организации).</span><span class="sxs-lookup"><span data-stu-id="85231-215">Click or tap the toggle to **On** next to **Let group owners add people outside the organization to groups**.</span></span>
    
    
  
    
    
![Снимок экрана, показывающий панель групп Office 365 с включенными параметрами "Let group members outside the organization access group content" (Предоставить участникам групп доступ к контенту групп извне организации) и "Let group owners add people outside the organization to groups" (Разрешить владельцам добавлять в группы людей извне организации).](media/eee77abd-4425-4585-91a8-5541c17ee7b2.png)
  
  
  
<span data-ttu-id="85231-217"><a name="controlguest"> </a></span><span class="sxs-lookup"><span data-stu-id="85231-217"></span></span>
## <a name="turn-on-or-off-the-sharing-option-for-office-365"></a><span data-ttu-id="85231-218">Включение и отключение параметра общего доступа для Office 365</span><span class="sxs-lookup"><span data-stu-id="85231-218">Turn on or off the Sharing option for Office 365</span></span>


<span data-ttu-id="85231-219">Параметр "Общий доступ" позволяет добавлять гостей в вашу организацию.</span><span class="sxs-lookup"><span data-stu-id="85231-219">The Sharing option allows guests to be added to your organization.</span></span> <span data-ttu-id="85231-220">По умолчанию он включен.</span><span class="sxs-lookup"><span data-stu-id="85231-220">By default, neither option is enabled.</span></span> <span data-ttu-id="85231-221">Сведения об отключении этого параметра см. в разделе [Включение и отключение параметра общего доступа](https://support.office.com/en-us/article/Turn-on-or-off-the-Sharing-option-7c713d74-a144-4eab-92e7-d50df526ff96#bkmk_beforeyoubegin).</span><span class="sxs-lookup"><span data-stu-id="85231-221">For information about how to turn off the Sharing option, see [Turn on or off the Sharing option](https://support.office.com/en-us/article/Turn-on-or-off-the-Sharing-option-7c713d74-a144-4eab-92e7-d50df526ff96#bkmk_beforeyoubegin).</span></span>
  
    
    

> [!IMPORTANT]
> <span data-ttu-id="85231-222">При отключенном параметре "Общий доступ" функция гостевого доступа не работает.</span><span class="sxs-lookup"><span data-stu-id="85231-222">If you turn off the Sharing option, guest access isn't available.</span></span> 
  

## <a name="use-powershell-to-control-guest-access"></a><span data-ttu-id="85231-223">Использование PowerShell для управления гостевым доступом</span><span class="sxs-lookup"><span data-stu-id="85231-223">Use PowerShell to control guest access</span></span>
<span data-ttu-id="85231-224"><a name="bkmk_UsePowerShell"> </a></span><span class="sxs-lookup"><span data-stu-id="85231-224"></span></span>

<span data-ttu-id="85231-225">Кроме Центра администрирования Office 365 и портала Azure Active Directory, для управления гостевым доступом вы можете использовать Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="85231-225">In addition to using the Office 365 admin center and the Azure Active Directory portal, you can use Windows PowerShell to control guest access.</span></span> <span data-ttu-id="85231-226">PowerShell предоставляет следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="85231-226">With PowerShell, you can do the following:</span></span>
  
    
    

- <span data-ttu-id="85231-227">Разрешение или запрет гостевого доступа для всех команд и групп Office 365</span><span class="sxs-lookup"><span data-stu-id="85231-227">Allow or block guest access to all teams and Office 365 groups</span></span>
    
  
- <span data-ttu-id="85231-228">Разрешение добавления гостей во все команды и группы Office 365</span><span class="sxs-lookup"><span data-stu-id="85231-228">Allow guests to be added to all teams and Office 365 groups</span></span>
    
  
- <span data-ttu-id="85231-229">Разрешение или блокировка гостевых пользователей из определенной команды или группы Office 365</span><span class="sxs-lookup"><span data-stu-id="85231-229">Allow or block guest users from a specific team or Office 365 group</span></span>
    
  
<span data-ttu-id="85231-230">Дополнительные сведения см. в статье об [использовании PowerShell для управления гостевым доступом](https://support.office.com/en-us/article/Use-PowerShell-to-control-guest-access-bfc7a840-868f-4fd6-a390-f347bf51aff6#bkmk_usepowershell).</span><span class="sxs-lookup"><span data-stu-id="85231-230">For more details, see [Use PowerShell to control guest access](https://support.office.com/en-us/article/Use-PowerShell-to-control-guest-access-bfc7a840-868f-4fd6-a390-f347bf51aff6#bkmk_usepowershell).</span></span>
  
    
    
<span data-ttu-id="85231-231">Вы также можете использовать PowerShell, чтобы разрешить или заблокировать гостевого пользователя по его домену.</span><span class="sxs-lookup"><span data-stu-id="85231-231">You can also use PowerShell to allow or block a guest user based on their domain.</span></span> <span data-ttu-id="85231-232">Например, предположим, что ваша организация (Contoso) сотрудничает с другой организацией (Fabrikam).</span><span class="sxs-lookup"><span data-stu-id="85231-232">For example, let's say your business (Contoso) has a partnership with another business (Fabrikam).</span></span> <span data-ttu-id="85231-233">Вы можете добавить Fabrikam в список разрешений, чтобы пользователи могли добавлять этих гостей в свои группы.</span><span class="sxs-lookup"><span data-stu-id="85231-233">You can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span> <span data-ttu-id="85231-234">Дополнительные сведения см. в статье [Разрешение и блокировка гостевого доступа к группам Office 365](https://go.microsoft.com/fwlink/?linkid=854001).</span><span class="sxs-lookup"><span data-stu-id="85231-234">For more information, see [Allow/Block guest access to Office 365 groups](https://go.microsoft.com/fwlink/?linkid=854001).</span></span>
  
    
    
<span data-ttu-id="85231-235"><a name="manageguest"> </a></span><span class="sxs-lookup"><span data-stu-id="85231-235"></span></span>
### <a name="view-guest-users"></a><span data-ttu-id="85231-236">Просмотр гостевых пользователей</span><span class="sxs-lookup"><span data-stu-id="85231-236">View guest users</span></span>



1. <span data-ttu-id="85231-237">Войдите с использованием учетной записи глобального администратора Office 365 по адресу [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span><span class="sxs-lookup"><span data-stu-id="85231-237">Sign in with your Office 365 global admin account at  [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
  
2. <span data-ttu-id="85231-238">Выберите **Пользователи** > **Гостевые пользователи**.</span><span class="sxs-lookup"><span data-stu-id="85231-238">Go to **Users** > **Guest users**.</span></span>
    
    
  
    
    
![Снимок экрана, показывающий выбранный параметр гостевых пользователей в разделе "Пользователи" Центра администрирования Office 365.](media/95b83ff5-72ef-4668-b541-4e25b767620a.png)
  
    

## <a name="invite-guest-users"></a><span data-ttu-id="85231-240">Приглашение гостевых пользователей</span><span class="sxs-lookup"><span data-stu-id="85231-240">Invite guest users</span></span>
<span data-ttu-id="85231-241"><a name="bkmk_UsePowerShell"> </a></span><span class="sxs-lookup"><span data-stu-id="85231-241"></span></span>

<span data-ttu-id="85231-242">Владелец команды или администратор Office 365 может [пригласить в команду гостя](https://support.office.com/en-us/article/invite-a-guest-to-a-team-df38ae23-8f85-46d3-b071-cb11b9de5499#bkmk_howdoiaddateammember) на индивидуальной основе.</span><span class="sxs-lookup"><span data-stu-id="85231-242">A team owner or an Office 365 admin can [invite a guest to a team](https://support.office.com/en-us/article/invite-a-guest-to-a-team-df38ae23-8f85-46d3-b071-cb11b9de5499#bkmk_howdoiaddateammember) on an individual basis.</span></span> <span data-ttu-id="85231-243">Однако администраторы не могут использовать Центр администрирования Office 365 или портал Azure Active Directory, чтобы пригласить несколько гостей за раз.</span><span class="sxs-lookup"><span data-stu-id="85231-243">However, admins can't use the Office 365 admin center or the Azure Active Directory portal to invite multiple guests in one action.</span></span> <span data-ttu-id="85231-244">Для централизованного приглашения гостей рекомендуется использовать предварительную версию службы совместной работы Azure Active Directory B2B.</span><span class="sxs-lookup"><span data-stu-id="85231-244">To invite guests centrally, consider using the Azure Active Directory B2B collaboration preview.</span></span> <span data-ttu-id="85231-245">Дополнительные сведения см. в статье [Сведения о предварительной версии службы совместной работы Azure AD B2B](https://go.microsoft.com/fwlink/p/?linkid=853011).</span><span class="sxs-lookup"><span data-stu-id="85231-245">For more information, see [About the Azure AD B2B collaboration preview](https://go.microsoft.com/fwlink/p/?linkid=853011).</span></span>
  
    
    

## <a name="edit-guest-user-information"></a><span data-ttu-id="85231-246">Изменение сведений о гостевых пользователях</span><span class="sxs-lookup"><span data-stu-id="85231-246">Edit guest user information</span></span>
<span data-ttu-id="85231-247"><a name="bkmk_UsePowerShell"> </a></span><span class="sxs-lookup"><span data-stu-id="85231-247"></span></span>

<span data-ttu-id="85231-248">Сейчас вы не можете изменять сведения о гостях в Центре администрирования Office 365 или Центре администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="85231-248">Currently, you can't edit guest information from the Office 365 admin center or the Exchange admin center.</span></span> <span data-ttu-id="85231-249">Чтобы изменить гостевые учетные записи (например, отображаемое имя или фотографию в профиле), перейдите на портал Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="85231-249">To edit guest accounts (such as display name or profile photo), go to your Azure Active Directory portal.</span></span> <span data-ttu-id="85231-250">Дополнительные сведения см. в статье [Общие сведения об удостоверении Office 365 и Azure Active Directory](https://support.office.com/en-us/article/Understanding-Office-365-Identity-and-Azure-Active-Directory-06a189e7-5ec6-4af2-94bf-a22ea225a7a9).</span><span class="sxs-lookup"><span data-stu-id="85231-250">For more information, see [Understanding Office 365 identity and Azure Active Directory](https://support.office.com/en-us/article/Understanding-Office-365-Identity-and-Azure-Active-Directory-06a189e7-5ec6-4af2-94bf-a22ea225a7a9).</span></span>
  
    
    
## <a name="frequently-asked-questions-for-admins"></a><span data-ttu-id="85231-251">Часто задаваемые вопросы для администраторов</span><span class="sxs-lookup"><span data-stu-id="85231-251">Frequently asked questions for admins</span></span>
<span data-ttu-id="85231-252"><a name="bkmk_UsePowerShell"> </a></span><span class="sxs-lookup"><span data-stu-id="85231-252"></span></span>

<span data-ttu-id="85231-253">Ниже приведены вопросы о приглашении гостей присоединиться к команде в Microsoft Teams, которые часто возникают у администраторов Office 365.</span><span class="sxs-lookup"><span data-stu-id="85231-253">Here are common questions Office 365 admins have about inviting guests to join a team in Microsoft Teams.</span></span>
  
    
    

#### <a name="what-is-a-guest"></a><span data-ttu-id="85231-254">Кто такой гость?</span><span class="sxs-lookup"><span data-stu-id="85231-254">What is a template?</span></span>


  
    
    
<span data-ttu-id="85231-255">Гость — это человек, не являющийся сотрудником, учащимся или участником вашей организации.</span><span class="sxs-lookup"><span data-stu-id="85231-255">A guest is not an employee, student, or member of your organization.</span></span> <span data-ttu-id="85231-256">У него нет учебной или рабочей учетной записи в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="85231-256">They don't have a school or work account with your organization.</span></span>
  
    
    

  
    
    

#### <a name="who-can-be-added-as-a-guest-user"></a><span data-ttu-id="85231-257">Кого можно добавить в качестве гостя?</span><span class="sxs-lookup"><span data-stu-id="85231-257">Who can be added as a guest user?</span></span>

<span data-ttu-id="85231-258">В качестве гостей можно добавить только пользователей с адресом электронной почты, соответствующим рабочей или учебной учетной записи Office 365 или Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="85231-258">Only users who have an email address corresponding to an Azure Active Directory or Office 365 work or school account can be added as a guest user.</span></span>
  
    
    

#### <a name="can-users-add-people-within-my-organization-who-are-not-part-of-the-team-as-a-guest"></a><span data-ttu-id="85231-259">Могут ли пользователи добавить в качестве гостя человека из моей организации, не входящего в соответствующую команду?</span><span class="sxs-lookup"><span data-stu-id="85231-259">Can users add people within my organization who are not part of the team as a guest?</span></span>

<span data-ttu-id="85231-260">В качестве гостей можно добавлять только людей, находящихся за пределами вашей организации, например партнеров или консультантов.</span><span class="sxs-lookup"><span data-stu-id="85231-260">Only people who are outside of your organization, such as partners or consultants, can be added as guests.</span></span> <span data-ttu-id="85231-261">Людей из организации пользователи могут приглашать в качестве обычных участников команды или подписчиков.</span><span class="sxs-lookup"><span data-stu-id="85231-261">Users can invite people from within your organization to join as regular team members or subscribers.</span></span>
  
    
    

#### <a name="why-does-a-user-get-the-message-contact-your-administrator-when-they-try-to-add-a-guest-to-their-team"></a><span data-ttu-id="85231-262">Почему пользователь получает сообщение "Обратитесь к администратору" при попытке добавить гостя в команду?</span><span class="sxs-lookup"><span data-stu-id="85231-262">Why does a user get the message "Contact your administrator" when they try to add a guest to their team?</span></span>

<span data-ttu-id="85231-263">Являясь администратором Office 365, вы должны включить функцию гостевого доступа, прежде чем вы или пользователи вашей организации (в частности, владельцы команд) смогут добавлять гостей.</span><span class="sxs-lookup"><span data-stu-id="85231-263">As the Office 365 admin, you must enable the guest feature before you or your organization's users (specifically, team owners) can add guests.</span></span> <span data-ttu-id="85231-264">Если пользователь видит указанное сообщение, вероятнее всего, что гостевой доступ отключен.</span><span class="sxs-lookup"><span data-stu-id="85231-264">When a user sees that message, it's likely that the guest feature hasn't been enabled.</span></span>
  
    
    

#### <a name="how-can-a-global-admin-add-a-new-guest-user-to-the-organization"></a><span data-ttu-id="85231-265">Как глобальный администратор может добавить нового гостевого пользователя в организацию?</span><span class="sxs-lookup"><span data-stu-id="85231-265">How can a global admin add a new guest user to the organization?</span></span>

<span data-ttu-id="85231-266">Являясь глобальным администратором, вы можете добавить нового гостевого пользователя в организацию несколькими способами:</span><span class="sxs-lookup"><span data-stu-id="85231-266">As a global admin, you can add a new guest user to the organization in a couple ways:</span></span>
  
    
    

- <span data-ttu-id="85231-267">Владельцы команды или являющиеся ими глобальные администраторы могут [добавить гостя в команду](https://support.office.com/en-us/article/add-a-guest-to-a-team-df38ae23-8f85-46d3-b071-cb11b9de5499#bkmk_howdoiaddateammember) с помощью классического или веб-клиента Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="85231-267">Global admins who are owners of a team and owners of a team can [add a guest to a team](https://support.office.com/en-us/article/add-a-guest-to-a-team-df38ae23-8f85-46d3-b071-cb11b9de5499#bkmk_howdoiaddateammember) through either the Microsoft Teams desktop or the web clients.</span></span>
    
  
- <span data-ttu-id="85231-268">Добавить гостей в организацию можно с помощью службы совместной работы Azure Active Directory B2B.</span><span class="sxs-lookup"><span data-stu-id="85231-268">Add guests to your organization through Azure Active Directory B2B collaboration.</span></span> <span data-ttu-id="85231-269">Она позволяет глобальному администратору пригласить и авторизовать набор внешних пользователей, отправив на портал совместной работы B2B файл данных с разделителями-запятыми (CSV) длиной не больше 2000 строк.</span><span class="sxs-lookup"><span data-stu-id="85231-269">Azure Active Directory B2B collaboration allows a global admin to invite and authorize a set of external users by uploading a comma-separated values (CSV) file of no more than 2,000 lines to the B2B collaboration portal.</span></span> <span data-ttu-id="85231-270">Дополнительные сведения см. в статье [Совместная работа Azure Active Directory B2B](https://go.microsoft.com/fwlink/p/?LinkId=826383).</span><span class="sxs-lookup"><span data-stu-id="85231-270">For more details, check out [Azure Active Directory B2B collaboration](https://go.microsoft.com/fwlink/p/?LinkId=826383).</span></span>
    
  

#### <a name="is-there-a-way-to-block-individual-guest-users"></a><span data-ttu-id="85231-271">Можно ли блокировать отдельных гостевых пользователей?</span><span class="sxs-lookup"><span data-stu-id="85231-271">Is there a way to block individual guest users?</span></span>

<span data-ttu-id="85231-272">Нет, отдельных гостевых пользователей блокировать невозможно.</span><span class="sxs-lookup"><span data-stu-id="85231-272">No, individual guest users can't be blocked.</span></span>
  
    
    

#### <a name="can-global-admins-block-guests-in-teams-and-still-allow-guests-to-access-sharepoint-sites"></a><span data-ttu-id="85231-273">Может ли глобальный администратор блокировать гостей в командах, разрешив им при этом доступ к сайтам SharePoint?</span><span class="sxs-lookup"><span data-stu-id="85231-273">Can global admins block guests in teams and still allow guests to access SharePoint sites?</span></span>

<span data-ttu-id="85231-274">Да, глобальный администратор может воспользоваться командлетами Powershell Azure Active Directory, чтобы отключить параметр _AllowGuestAccessToGroups_ объекта "Company", при условии, что для сайтов SharePoint включен внешний общий доступ.</span><span class="sxs-lookup"><span data-stu-id="85231-274">Yes, global admins can use Azure Active Directory Powershell cmdlets to disable the  _AllowGuestAccessToGroups_ parameter on the Company object, assuming external sharing is turned on for SharePoint sites.</span></span>
  
    
    

#### <a name="what-other-controls-are-available-to-it-admins-to-manage-guests-in-microsoft-teams"></a><span data-ttu-id="85231-275">Какие еще средства доступны ИТ-администраторам для управления гостями в Microsoft Teams?</span><span class="sxs-lookup"><span data-stu-id="85231-275">What other controls are available to IT admins to manage guests in Microsoft Teams?</span></span>

<span data-ttu-id="85231-276">ИТ-администраторы могут добавлять гостей на уровне клиента, задавать политики и разрешения для гостевых пользователей и управлять ими, определять, какие пользователи могут приглашать гостей, а также составлять отчеты о деятельности гостевых пользователей.</span><span class="sxs-lookup"><span data-stu-id="85231-276">IT admins can add guests at the tenant level, set and manage guest user policies and permissions, determine which users can invite guests, and pull reports on guest user activity.</span></span> <span data-ttu-id="85231-277">Эти средства управления доступны в Центре администрирования Office 365.</span><span class="sxs-lookup"><span data-stu-id="85231-277">These controls are available through the Office 365 admin center.</span></span> <span data-ttu-id="85231-278">На контент и деятельность гостевых пользователей распространяются те же меры обеспечения соответствия и аудиторской защиты, что и на остальную часть Office 365.</span><span class="sxs-lookup"><span data-stu-id="85231-278">Guest user content and activities are under the same compliance and auditing protection as the rest of Office 365.</span></span>
  
    
    

#### <a name="can-users-share-a-team-file-with-an-external-user-who-isnt-a-member-of-the-team"></a><span data-ttu-id="85231-279">Могут ли пользователи предоставить общий доступ к файлу команды внешнему пользователю, не являющемуся участником команды?</span><span class="sxs-lookup"><span data-stu-id="85231-279">Can users share a team file with an external user who isn't a member of the team?</span></span>

<span data-ttu-id="85231-280">Нет.</span><span class="sxs-lookup"><span data-stu-id="85231-280">No.</span></span> <span data-ttu-id="85231-281">Пользователи могут предоставлять общий доступ к файлам Microsoft Teams только гостям, приглашенным в команду.</span><span class="sxs-lookup"><span data-stu-id="85231-281">Users can only share Microsoft Teams files with guests who have been invited to join the team.</span></span>
  
    
    

#### <a name="is-an-additional-office-365-license-required-for-guest-access"></a><span data-ttu-id="85231-282">Требуется ли для гостевого доступа дополнительная лицензия Office 365?</span><span class="sxs-lookup"><span data-stu-id="85231-282">Is an additional Office 365 license required for guest access?</span></span>

<span data-ttu-id="85231-283">Дополнительная лицензия не требуется.</span><span class="sxs-lookup"><span data-stu-id="85231-283">No additional license is required.</span></span> <span data-ttu-id="85231-284">Функция гостевого доступа включена во все подписки Office 365 бизнес премиум, Office 365 корпоративный и Office 365 для образования.</span><span class="sxs-lookup"><span data-stu-id="85231-284">Guest access is included with all Office 365 Business Premium, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span>
  
    
    

#### <a name="do-office-365-and-azure-active-directory-service-limits-apply-to-guests"></a><span data-ttu-id="85231-285">Применяются ли ограничения служб Office 365 и Azure Active Directory к гостям?</span><span class="sxs-lookup"><span data-stu-id="85231-285">Do Office 365 and Azure Active Directory service limits apply to guests?</span></span>

<span data-ttu-id="85231-286">Да, на гостей распространяются ограничения служб [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) и [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019).</span><span class="sxs-lookup"><span data-stu-id="85231-286">Yes, guests are subject to  [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) and [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) service limits.</span></span>
  
    
    

  
    
    

#### <a name="how-long-does-it-take-until-the-guest-user-settings-take-effect-in-the-office-365-organization"></a><span data-ttu-id="85231-287">Сколько времени требуется, чтобы параметры гостевых пользователей вступили в силу в организации Office 365?</span><span class="sxs-lookup"><span data-stu-id="85231-287">How long does it take until the guest user settings take effect in the Office 365 organization?</span></span>

<span data-ttu-id="85231-288">Параметры гостей задаются в Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="85231-288">The guest settings are set in Azure Active Directory.</span></span> <span data-ttu-id="85231-289">Чтобы эти изменения вступили в силу в рамках всей организации Office 365, требуется от 2 до 24 часов.</span><span class="sxs-lookup"><span data-stu-id="85231-289">It takes 2 hours to 24 hours for the changes to be effective across your Office 365 organization.</span></span>
  
    
    

#### <a name="can-a-global-admin-manage-sharepoint-online-external-user-settings-for-the-teams-connected-team-site"></a><span data-ttu-id="85231-290">Может ли глобальный администратор управлять параметрами внешних пользователей SharePoint Online для подключенного к Teams сайта группы?</span><span class="sxs-lookup"><span data-stu-id="85231-290">Can a global admin manage SharePoint Online external user settings for the Teams connected team site?</span></span>

<span data-ttu-id="85231-291">Да, вы можете управлять параметрами внешних пользователей SharePoint Online для подключенного к Teams сайта группы.</span><span class="sxs-lookup"><span data-stu-id="85231-291">Yes, you can manage SharePoint Online external user settings for the Teams connected team site.</span></span> <span data-ttu-id="85231-292">Дополнительные сведения см. в статье [Управление параметрами для сайта группы SharePoint](https://support.office.com/en-us/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42).</span><span class="sxs-lookup"><span data-stu-id="85231-292">For more details, see  [Manage your SharePoint team site settings](https://support.office.com/en-us/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42).</span></span>
  
    
    

  
    
    

#### <a name="how-does-conditional-access-work-with-guest-access"></a><span data-ttu-id="85231-293">Как условный доступ работает вместе с гостевым доступом?</span><span class="sxs-lookup"><span data-stu-id="85231-293">How does conditional access work with guest access?</span></span>

<span data-ttu-id="85231-294">С помощью службы совместной работы Azure Active Directory B2B организации могут задавать для B2B-пользователей политики условного доступа и многофакторной проверки подлинности (MFA).</span><span class="sxs-lookup"><span data-stu-id="85231-294">With Azure Active Directory B2B collaboration, organizations can enforce conditional access and multi-factor authentication (MFA) policies for B2B users.</span></span> <span data-ttu-id="85231-295">Эти политики можно применить на уровне клиента, приложения или отдельного пользователя, следуя тем же процедурам, что и при задании их для штатных сотрудников и участников организации.</span><span class="sxs-lookup"><span data-stu-id="85231-295">These policies can be enforced at the tenant, app, or individual user level, the same way that they are enabled for full-time employees and members of the organization.</span></span> <span data-ttu-id="85231-296">Эти политики применяются в ресурсной организации.</span><span class="sxs-lookup"><span data-stu-id="85231-296">Such policies are enforced at the resource organization.</span></span> <span data-ttu-id="85231-297">Дополнительные сведения см. в статье [Условный доступ для пользователей службы совместной работы B2B](https://go.microsoft.com/fwlink/?linkid=857454).</span><span class="sxs-lookup"><span data-stu-id="85231-297">For more information, see  [Conditional access for B2B collaboration users](https://go.microsoft.com/fwlink/?linkid=857454).</span></span>
  
    
    

#### <a name="if-i-have-a-team-with-an-office-365-group-and-i-add-a-guest-to-the-group-does-that-user-automatically-get-access-to-the-team"></a><span data-ttu-id="85231-298">Если у меня есть команда с группой Office 365 и я добавлю в эту группу гостя, получит ли он доступ к команде автоматически?</span><span class="sxs-lookup"><span data-stu-id="85231-298">If I have a team with an Office 365 group, and I add a guest to the group, does that user automatically get access to the team?</span></span>

<span data-ttu-id="85231-299">Да, гость получит доступ к команде.</span><span class="sxs-lookup"><span data-stu-id="85231-299">Yes, the guest will get access to the team.</span></span> <span data-ttu-id="85231-300">Добавление гостя через группу Office 365 не приводит к отправке ему приглашения по электронной почте, поэтому гостя должен уведомить один из участников команды.</span><span class="sxs-lookup"><span data-stu-id="85231-300">Adding a guest via the Office 365 group doesn't generate an invitation email to the guest, so someone on the team should notify the guest.</span></span>
  
    
    

#### <a name="what-event-appears-in-the-audit-log-to-indicate-a-guest-has-been-sent-an-invitation"></a><span data-ttu-id="85231-301">Какое событие регистрируется в журнале аудита при отправке гостю приглашения?</span><span class="sxs-lookup"><span data-stu-id="85231-301">What event appears in the audit log to indicate a guest has been sent an invitation?</span></span>

<span data-ttu-id="85231-302">Вы можете отслеживать добавление гостей в Azure Active Directory или Центре безопасности &amp;и соответствия требованиям Office 365.</span><span class="sxs-lookup"><span data-stu-id="85231-302">You can track guest additions in Azure Active Directory or the Office 365 Security &amp; Compliance Center.</span></span> <span data-ttu-id="85231-303">Добавление гостя в Microsoft Teams проходит аудит и регистрируется в журнале администрирования групп Azure AD в виде записи "Added member to group" (Добавление участника в группу).</span><span class="sxs-lookup"><span data-stu-id="85231-303">Adding a guest in Microsoft Teams is audited and logged as an Azure AD group administration activity "Added member to group".</span></span> <span data-ttu-id="85231-304">Дополнительные сведения см. в статьях [Аудит и отчеты для пользователя службы совместной работы B2B](https://go.microsoft.com/fwlink/p/?linkid=858884) и [Поиск журнала аудита в Центре безопасности &amp;и соответствия требованиям Office 365](https://support.office.com/en-us/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c).</span><span class="sxs-lookup"><span data-stu-id="85231-304">For more details, see  [Auditing and reporting a B2B collaboration user](https://go.microsoft.com/fwlink/p/?linkid=858884) and [Search the audit log in the Office 365 Security &amp; Compliance Center](https://support.office.com/en-us/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c).</span></span>
  
    
    

#### <a name="if-i-have-existing-guest-users-that-were-added-via-azure-ad-b2b-office-365-groups-or-sharepoint-online-do-i-have-to-do-anything-else-with-them-for-microsoft-teams"></a><span data-ttu-id="85231-305">Если имеются гостевые пользователи, добавленные через службу Azure AD B2B, Группы Office 365 или SharePoint Online, нужно ли выполнять какие-либо действия, чтобы работать с ними в Microsoft Teams?</span><span class="sxs-lookup"><span data-stu-id="85231-305">If I have existing guest users that were added via Azure AD B2B, Office 365 Groups, or SharePoint Online, do I have to do anything else with them for Microsoft Teams?</span></span>

<span data-ttu-id="85231-306">Гостевые пользователи, добавленные через Azure Active Directory B2B, Группы Office 365 или SharePoint Online, готовы к работе.</span><span class="sxs-lookup"><span data-stu-id="85231-306">Guest users you have already added via Azure Active Directory B2B, Office 365 Groups or SharePoint Online are ready to go.</span></span> <span data-ttu-id="85231-307">Администратор Office 365 или владелец команды может добавить их в свои команды.</span><span class="sxs-lookup"><span data-stu-id="85231-307">The Office 365 admin or a team owner can add those guests to their respective teams.</span></span>
  
    
    

#### <a name="if-external-accounts-are-available-does-that-mean-external-sharing-is-enabled"></a><span data-ttu-id="85231-308">Если доступны внешние учетные записи, означает ли это, что включен внешний общий доступ?</span><span class="sxs-lookup"><span data-stu-id="85231-308">If external accounts are available, does that mean external sharing is enabled?</span></span>

<span data-ttu-id="85231-309">Администраторы могут создать гостевые учетные записи в Azure Active Directory независимо от параметров внешнего общего доступа.</span><span class="sxs-lookup"><span data-stu-id="85231-309">Admins can create guest accounts in Azure Active Directory, independent from external sharing settings.</span></span> <span data-ttu-id="85231-310">Если внешний общий доступ отключен, гостевые учетные записи может создавать только администратор.</span><span class="sxs-lookup"><span data-stu-id="85231-310">If external sharing is off, only an admin can create guest accounts.</span></span>
  
    
    

  
    
    

## <a name="more-information"></a><span data-ttu-id="85231-311">Дополнительная информация</span><span class="sxs-lookup"><span data-stu-id="85231-311">More information</span></span>

 [<span data-ttu-id="85231-312">Параметры администратора для Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="85231-312">Administrator settings for Microsoft Teams</span></span>](https://support.office.com/en-us/article/Administrator-settings-for-Microsoft-Teams-3966a3f5-7e0f-4ea9-a402-41888f455ba2)
  
    
    
 [<span data-ttu-id="85231-313">Часто задаваемые вопросы о Microsoft Teams — справка для администратора</span><span class="sxs-lookup"><span data-stu-id="85231-313">Frequently asked questions about Microsoft Teams - Admin Help</span></span>](https://support.office.com/en-us/article/Frequently-asked-questions-about-Microsoft-Teams-–-Admin-Help-05cbe533-2181-4e95-a4b0-52cd7695fafc)
  
    
    
 [<span data-ttu-id="85231-314">Добавление гостей в команды</span><span class="sxs-lookup"><span data-stu-id="85231-314">Adding guests to teams</span></span>](https://support.office.com/en-us/article/Adding-guests-to-teams-df38ae23-8f85-46d3-b071-cb11b9de5499#bkmk_addingguests)
  
    
    
<span data-ttu-id="85231-315">Видео.  [Подробный обзор гостевого доступа](https://go.microsoft.com/fwlink/p/?linkid=858791)</span><span class="sxs-lookup"><span data-stu-id="85231-315">Video:  [Deep Dive into Guest Access](https://go.microsoft.com/fwlink/p/?linkid=858791)</span></span>
  
    
    

