---
title: Предоставление учетных записей системы комнат Skype в Office 365
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c36150bb-461c-4f1c-877b-fac7fb232f7c
description: В этом разделе описывается выделение учетных записей системы комнат Skype в Office 365.
ms.openlocfilehash: 830c0e33a15639f3c78197d084748bb3b2cde600
ms.sourcegitcommit: ddb4eaf634476680494025a3aa1c91d15fb58413
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/11/2019
ms.locfileid: "38231270"
---
# <a name="provisioning-skype-room-system-accounts-in-office-365"></a><span data-ttu-id="4856e-103">Предоставление учетных записей системы комнат Skype в Office 365</span><span class="sxs-lookup"><span data-stu-id="4856e-103">Provisioning Skype Room System accounts in Office 365</span></span>
 
<span data-ttu-id="4856e-104">В этом разделе описывается выделение учетных записей системы комнат Skype в Office 365.</span><span class="sxs-lookup"><span data-stu-id="4856e-104">Read this topic to learn about provisioning Skype Room System accounts in Office 365.</span></span>
  
<span data-ttu-id="4856e-105">В следующем разделе приводится описание подготовки учетной записи системы Skype для клиента Office 365.</span><span class="sxs-lookup"><span data-stu-id="4856e-105">The following section covers Skype Room System account provisioning for an Office 365 tenant.</span></span>
  
## <a name="office-365-prerequisites"></a><span data-ttu-id="4856e-106">Предварительные требования для Office 365</span><span class="sxs-lookup"><span data-stu-id="4856e-106">Office 365 prerequisites</span></span>

<span data-ttu-id="4856e-107">Сетевой клиент должен удовлетворять следующим требованиям:</span><span class="sxs-lookup"><span data-stu-id="4856e-107">Your online tenant must meet the following requirements:</span></span>
  
- <span data-ttu-id="4856e-108">План Office 365 должен включать Skype для бизнеса Online (план 2) или Office 365 E1, E3 или 3.</span><span class="sxs-lookup"><span data-stu-id="4856e-108">The Office 365 plan must include Skype for Business Online Plan 2, or Office 365 E1, E3 or E5.</span></span> <br/><span data-ttu-id="4856e-109">Подробнее о тарифах Skype для бизнеса Online можно найти в [описании службы Skype для бизнеса Online](https://technet.microsoft.com/library/jj822172.aspx).</span><span class="sxs-lookup"><span data-stu-id="4856e-109">For details on Skype for Business Online Plans, see the [Skype for Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx).</span></span>
    
- <span data-ttu-id="4856e-110">В клиенте должна быть включена возможность проведения Конференции в Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="4856e-110">Your tenant must have the conferencing capability of Skype for Business enabled.</span></span>
    
- <span data-ttu-id="4856e-111">У пользователя должно быть включено приложение Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="4856e-111">Your tenant must have Exchange Online enabled.</span></span> 
    
- <span data-ttu-id="4856e-112">Удаленный администратор пользователя должен иметь следующие права доступа PowerShell:</span><span class="sxs-lookup"><span data-stu-id="4856e-112">Your tenant remote administrator must have the following PowerShell access:</span></span>
    
  - <span data-ttu-id="4856e-113">Удаленный доступ PowerShell к Exchange</span><span class="sxs-lookup"><span data-stu-id="4856e-113">Exchange Remote PowerShell access</span></span>
    
  - <span data-ttu-id="4856e-114">Удаленный доступ к PowerShell в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="4856e-114">Skype for Business Online Remote PowerShell access</span></span>
    
  - <span data-ttu-id="4856e-115">Модуль Windows Azure Active Directory для Windows PowerShell для доступа к каталогу Office 365</span><span class="sxs-lookup"><span data-stu-id="4856e-115">Windows Azure Active Directory Module for Windows PowerShell to access Office 365 directory access</span></span>
    
<span data-ttu-id="4856e-116">Для учетной записи комнаты Skype необходимы следующие лицензии::</span><span class="sxs-lookup"><span data-stu-id="4856e-116">For the Skype Room account, the following licensing is required:</span></span>
  
- <span data-ttu-id="4856e-117">Для включения собраний Skype требуется лицензия Skype для бизнеса Online (план 2) или Office 365 E1 или E3.</span><span class="sxs-lookup"><span data-stu-id="4856e-117">A Skype for Business Online Plan 2 or Office 365 E1 or E3 license is required to enable Skype Meetings.</span></span>
    
- <span data-ttu-id="4856e-118">Чтобы предоставить доступ к комнате с помощью корпоративной голосовой связи, чтобы можно было использовать телефонный номер, требуется Skype для бизнеса Online (план 2) с лицензией на телефонную систему или Office 365 3 (1).</span><span class="sxs-lookup"><span data-stu-id="4856e-118">To entitle the room with the Enterprise Voice capability so the room can be enabled with a phone number, a Skype for Business Online Plan 2 with the Phone System license or Office 365 E5 is required (1).</span></span>
    
- <span data-ttu-id="4856e-119">Если вам понадобятся возможности телефонного подключения к собранию, вам потребуется голосовой Конференц-связь и лицензия на телефонную систему.</span><span class="sxs-lookup"><span data-stu-id="4856e-119">If you need dial-in capabilities from a meeting, you will need an audio conferencing and Phone System license.</span></span>  <span data-ttu-id="4856e-120">Если вам нужны возможности исходящих звонков с собрания, вам понадобится план внутренних или внутренних и международных звонков.</span><span class="sxs-lookup"><span data-stu-id="4856e-120">If you need dial-out capabilities from a meeting, you will need a domestic or domestic and international Calling Plan.</span></span> 
    
- <span data-ttu-id="4856e-121">Лицензия Exchange Online не требуется для учетной записи комнаты Skype, так как эта учетная запись должна настраиваться как учетная запись почтового ящика ресурса.</span><span class="sxs-lookup"><span data-stu-id="4856e-121">An Exchange Online license is not required for the Skype Room account because the account should be configured as a resource mailbox account.</span></span>
    
## <a name="provisioning-overview"></a><span data-ttu-id="4856e-122">Обзор предоставления</span><span class="sxs-lookup"><span data-stu-id="4856e-122">Provisioning overview</span></span>

<span data-ttu-id="4856e-123">На приведенной ниже схеме представлен обзор процесса подготовки учетной записи системы для помещения в Skype в Office 365.</span><span class="sxs-lookup"><span data-stu-id="4856e-123">The following diagram provides an overview of the Skype Room System account provisioning flow in Office 365.</span></span>
  
![Этапы подготовки системы для комнаты Skype для O365](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a><span data-ttu-id="4856e-125">Создание новой комнаты переговоров</span><span class="sxs-lookup"><span data-stu-id="4856e-125">Identify a new conference room</span></span>

<span data-ttu-id="4856e-126">Возможно, у вас уже есть почтовый ящик из комнаты ресурсов в Exchange, в котором есть функция планирования, или вы можете создать почтовый ящик ресурсов в первый раз, чтобы упростить развертывание системы комнаты Skype.</span><span class="sxs-lookup"><span data-stu-id="4856e-126">You may already have a resource room mailbox in Exchange that provides the scheduling feature, or you may be creating a resource mailbox for the first time to facilitate Skype Room System deployment.</span></span> <span data-ttu-id="4856e-127">В обоих случаях необходимо создать учетную запись комнаты, которая будет использоваться в клиенте.</span><span class="sxs-lookup"><span data-stu-id="4856e-127">In any case, you must identify a room account to be used in your tenant.</span></span> <span data-ttu-id="4856e-128">Разделы подготовки Exchange Online и Skype для бизнеса содержат рекомендации для обоих типов учетных записей.</span><span class="sxs-lookup"><span data-stu-id="4856e-128">The Exchange Online Provision and Skype for Business Provision sections provide guidance for both kinds of accounts.</span></span> <span data-ttu-id="4856e-129">Например, предположим, что у вас есть две комнаты, и вы хотите развернуть систему комнат Skype для обоих из них:</span><span class="sxs-lookup"><span data-stu-id="4856e-129">For example, let's say you have the following two rooms, and you would like to deploy Skype Room System for both of them:</span></span>
  
- <span data-ttu-id="4856e-130">Текущая учетная запись почтового ящика ресурсов: confrm1@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="4856e-130">Existing Resource Mailbox Account: confrm1@contoso.onmicrosoft.com</span></span>
    
- <span data-ttu-id="4856e-131">Новая учетная запись почтового ящика ресурсов: confrm2@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="4856e-131">New Resource Mailbox Account: confrm2@contoso.onmicrosoft.com</span></span>
    
## <a name="exchange-online-provisioning"></a><span data-ttu-id="4856e-132">Предоставление Exchange Online</span><span class="sxs-lookup"><span data-stu-id="4856e-132">Exchange Online provisioning</span></span>

<span data-ttu-id="4856e-133">Сначала подключитесь к Exchange Online PowerShell, следуя инструкциям в этой статье, [подключитесь к Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span><span class="sxs-lookup"><span data-stu-id="4856e-133">First, connect to Exchange Online PowerShell by following the instructions in the topic, [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
  
<span data-ttu-id="4856e-134">Чтобы настроить существующую учетную запись почтового ящика для помещения в комнату для Skype, выполните следующие команды в Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4856e-134">To set an existing resource room mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:</span></span>
  
```
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

<span data-ttu-id="4856e-135">Чтобы создать новую учетную запись почтового ящика Exchange для системы комнат Skype, выполните в Exchange Online PowerShell следующие команды:</span><span class="sxs-lookup"><span data-stu-id="4856e-135">To create a new Exchange resource mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:</span></span>
  
```
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

<span data-ttu-id="4856e-136">Предыдущие команды настроили или создали новую учетную запись почтового ящика Exchange для помещения в Skype, включив учетную запись.</span><span class="sxs-lookup"><span data-stu-id="4856e-136">The previous commands set up or create a new Exchange resource mailbox account for Skype Room System usage by enabling the account.</span></span>
  
<span data-ttu-id="4856e-137">Создав почтовый ящик, вы можете настроить почтовый ящик с помощью командлета Set-Календарпроцессинг в Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4856e-137">After creating the mailbox, you can use the Set-CalendarProcessing cmdlet in Exchange Online PowerShell to configure the mailbox.</span></span> <span data-ttu-id="4856e-138">Дополнительные сведения см. в разделе "Развертывание одного локального леса", шаги 3–6.</span><span class="sxs-lookup"><span data-stu-id="4856e-138">Refer to steps 3 through 6 under Single forest on-premises deployments for more details</span></span>

## <a name="assigning-a-skype-for-business-online-license"></a><span data-ttu-id="4856e-139">Назначение лицензии Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="4856e-139">Assigning a Skype for Business Online license</span></span>

<span data-ttu-id="4856e-140">Теперь вы можете назначить лицензию Skype для бизнеса Online (план 2) или Skype для бизнеса Online (план 3) с помощью административного портала Office 365, как описано в разделе [назначение и удаление лицензий для office 365 для бизнеса](https://support.office.com/en-us/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) или в [лицензии на надстройку Skype для бизнеса](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7).</span><span class="sxs-lookup"><span data-stu-id="4856e-140">Now you can assign a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license by using the Office 365 administrative portal as described in [Assign or remove licenses for Office 365 for business](https://support.office.com/en-us/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) or in [Skype for Business add-on licensing](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7).</span></span> 
  
<span data-ttu-id="4856e-141">После назначения лицензии Skype для бизнеса Online вы сможете войти в систему и подтвердить, что она активна с помощью любого клиента Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="4856e-141">After you assign a license for Skype for Business Online, you will be able to log in and validate that the account is active using any Skype for Business client.</span></span>
  
## <a name="skype-for-business-online-provisioning"></a><span data-ttu-id="4856e-142">Предоставление Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="4856e-142">Skype for Business Online provisioning</span></span>

<span data-ttu-id="4856e-143">После создания и включения учетной записи почтового ящика для ресурсов, как показано выше, и активации учетной записи в Skype для бизнеса Online учетная запись будет синхронизирована с лесом Exchange Online и в лесу Skype для бизнеса Online с помощью Лес Windows Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4856e-143">After a resource room mailbox account has been created and enabled as shown previously, and you have licensed the account for Skype For Business Online the account will synchronize from the Exchange Online forest to Skype for Business Online forest by using the Windows Azure Active Directory forest.</span></span> <span data-ttu-id="4856e-144">Для подготовки учетной записи системы комнаты Skype в пуле Skype для бизнеса Online необходимо выполнить указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="4856e-144">The following steps are required to provision the Skype Room System account in the Skype for Business Online pool.</span></span> <span data-ttu-id="4856e-145">Эти действия одинаковы для существующей учетной записи почтового ящика ресурса или вновь созданной учетной записи (confrm1 или confrm2), поскольку обе эти учетные записи будут синхронизироваться с Skype для бизнеса Online так же, как и в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="4856e-145">These steps are the same for both an existing resource mailbox account or a newly created account (confrm1 or confrm2), because once they are enabled in Exchange Online, both of these accounts will be synchronized to Skype for Business Online in the same way:</span></span>
  
1. <span data-ttu-id="4856e-146">Создайте удаленный сеанс PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4856e-146">Create a Remote PowerShell session.</span></span> <span data-ttu-id="4856e-147">Обратите внимание, что для этого вам потребуется загрузить модуль соединителя Skype для бизнеса Online и помощник по входу в Microsoft Online Services и проверить, настроен ли ваш компьютер.</span><span class="sxs-lookup"><span data-stu-id="4856e-147">Note that you will need to download Skype for Business Online Connector Module and Microsoft Online Services Sign-In Assistant and make sure that your computer is configured.</span></span> <span data-ttu-id="4856e-148">Дополнительные сведения можно найти в разделе [Настройка компьютера для Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="4856e-148">For more information, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
    
   ```
   Import-Module LyncOnlineConnector
   $cssess=New-CsOnlineSession -Credential $cred
   Import-PSSession $cssess -AllowClobber
   ```

2. <span data-ttu-id="4856e-149">Чтобы включить учетную запись системы комнаты Skype для Skype для бизнеса, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="4856e-149">To enable an Skype Room System account for Skype for Business, run the following command:</span></span>
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    <span data-ttu-id="4856e-150">Вы можете получить адрес Регистрарпул, на котором пользователи Skype для бизнеса находятся в одной из существующих учетных записей, выполнив следующую команду, чтобы возвратить это свойство:</span><span class="sxs-lookup"><span data-stu-id="4856e-150">You can obtain the RegistrarPool address where your Skype for Business users are homed from one of your existing accounts by using the following command to returns this property:</span></span>
    
   ```
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

>[!NOTE] 
><span data-ttu-id="4856e-151">Многофакторная проверка подлинности (MFA) не поддерживается для учетных записей системы комнаты Skype.</span><span class="sxs-lookup"><span data-stu-id="4856e-151">Multi-Factor Authentication (MFA) isn't supported for Skype Room System accounts.</span></span> 

## <a name="password-expiration"></a><span data-ttu-id="4856e-152">Срок действия пароля</span><span class="sxs-lookup"><span data-stu-id="4856e-152">Password expiration</span></span>

<span data-ttu-id="4856e-153">В Office 365 политика истечения срока действия паролей по умолчанию для всех учетных записей пользователей составляет 90 дня, если вы не настроили другую политику срока действия паролей.</span><span class="sxs-lookup"><span data-stu-id="4856e-153">In Office 365, the default password expiration policy for all of your user accounts is 90 days unless you configure a different password expiration policy.</span></span> <span data-ttu-id="4856e-154">Для системных учетных записей комнаты Skype вы можете выбрать пароль, который не может быть указан, выполнив указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="4856e-154">For Skype Room System accounts, you can select the Password never expires setting with the following steps.</span></span>
  
1. <span data-ttu-id="4856e-155">Создайте сеанс Windows Azure Active Directory, указав учетные данные глобального администратора клиента.</span><span class="sxs-lookup"><span data-stu-id="4856e-155">Create a Windows Azure Active Directory session by using your tenant global administrator credentials.</span></span>
    
    ```
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. <span data-ttu-id="4856e-156">Настройка пароля не действует для учетной записи комнаты системы комнат Skype, созданной ранее с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="4856e-156">Set the Password never expires setting for the Skype Room System room account created previously by using the following command:</span></span>
    
   ```
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

<span data-ttu-id="4856e-157">Дополнительные сведения можно найти в разделе [Настройка компьютера для Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="4856e-157">For more information, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
  
## <a name="validate"></a><span data-ttu-id="4856e-158">Действитель</span><span class="sxs-lookup"><span data-stu-id="4856e-158">Validate</span></span>

<span data-ttu-id="4856e-159">Для проверки подлинности вы можете использовать любой клиент Skype для бизнеса для входа в созданную учетную запись.</span><span class="sxs-lookup"><span data-stu-id="4856e-159">For validation, you should be able to use any Skype for Business client to sign in to the account you created.</span></span>

