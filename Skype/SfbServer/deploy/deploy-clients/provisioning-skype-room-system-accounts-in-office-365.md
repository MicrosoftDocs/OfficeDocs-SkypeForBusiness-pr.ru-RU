---
title: Подготовка учетных записей системы комнат Skype в Office 365
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c36150bb-461c-4f1c-877b-fac7fb232f7c
description: В этом разделе рассказывается о подготовке учетных записей системы комнат Skype в Office 365.
ms.openlocfilehash: 141c833bcbdd744a7577c0762cb8ba55dd3d5c54
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037729"
---
# <a name="provisioning-skype-room-system-accounts-in-office-365"></a><span data-ttu-id="7b29b-103">Подготовка учетных записей системы комнат Skype в Office 365</span><span class="sxs-lookup"><span data-stu-id="7b29b-103">Provisioning Skype Room System accounts in Office 365</span></span>
 
<span data-ttu-id="7b29b-104">В этом разделе рассказывается о подготовке учетных записей системы комнат Skype в Office 365.</span><span class="sxs-lookup"><span data-stu-id="7b29b-104">Read this topic to learn about provisioning Skype Room System accounts in Office 365.</span></span>
  
<span data-ttu-id="7b29b-105">В следующем разделе описывается подготовка учетной записи системы комнат Skype для клиента Office 365.</span><span class="sxs-lookup"><span data-stu-id="7b29b-105">The following section covers Skype Room System account provisioning for an Office 365 tenant.</span></span>
  
## <a name="office-365-prerequisites"></a><span data-ttu-id="7b29b-106">Предварительные требования для Office 365</span><span class="sxs-lookup"><span data-stu-id="7b29b-106">Office 365 prerequisites</span></span>

<span data-ttu-id="7b29b-107">Ваш клиент сети должен отвечать следующим требованиям:</span><span class="sxs-lookup"><span data-stu-id="7b29b-107">Your online tenant must meet the following requirements:</span></span>
  
- <span data-ttu-id="7b29b-108">План Office 365 должен включать Skype для бизнеса Online (план 2) или Office 365 E1, E3 или в.</span><span class="sxs-lookup"><span data-stu-id="7b29b-108">The Office 365 plan must include Skype for Business Online Plan 2, or Office 365 E1, E3 or E5.</span></span> <br/><span data-ttu-id="7b29b-109">Подробнее о планах Skype для бизнеса Online можно узнать в статье [Описание службы Skype для бизнеса Online](https://technet.microsoft.com/library/jj822172.aspx).</span><span class="sxs-lookup"><span data-stu-id="7b29b-109">For details on Skype for Business Online Plans, see the [Skype for Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx).</span></span>
    
- <span data-ttu-id="7b29b-110">У вашего клиента должна быть возможность конференц-связи с включенной поддержкой Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="7b29b-110">Your tenant must have the conferencing capability of Skype for Business enabled.</span></span>
    
- <span data-ttu-id="7b29b-111">У клиента должен быть включен Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="7b29b-111">Your tenant must have Exchange Online enabled.</span></span> 
    
- <span data-ttu-id="7b29b-112">Удаленный администратор клиента должен иметь следующий доступ к PowerShell:</span><span class="sxs-lookup"><span data-stu-id="7b29b-112">Your tenant remote administrator must have the following PowerShell access:</span></span>
    
  - <span data-ttu-id="7b29b-113">Удаленный доступ PowerShell к Exchange</span><span class="sxs-lookup"><span data-stu-id="7b29b-113">Exchange Remote PowerShell access</span></span>
    
  - <span data-ttu-id="7b29b-114">Доступ к удаленной оболочке PowerShell в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="7b29b-114">Skype for Business Online Remote PowerShell access</span></span>
    
  - <span data-ttu-id="7b29b-115">Модуль Windows Azure Active Directory для Windows PowerShell для доступа к каталогу Office 365</span><span class="sxs-lookup"><span data-stu-id="7b29b-115">Windows Azure Active Directory Module for Windows PowerShell to access Office 365 directory access</span></span>
    
<span data-ttu-id="7b29b-116">Для учетной записи комнаты Skype необходимо следующее лицензирование:</span><span class="sxs-lookup"><span data-stu-id="7b29b-116">For the Skype Room account, the following licensing is required:</span></span>
  
- <span data-ttu-id="7b29b-117">Для включения собраний Skype требуется лицензия Skype для бизнеса Online (план 2) или Office 365 E1 или E3.</span><span class="sxs-lookup"><span data-stu-id="7b29b-117">A Skype for Business Online Plan 2 or Office 365 E1 or E3 license is required to enable Skype Meetings.</span></span>
    
- <span data-ttu-id="7b29b-118">Чтобы обеспечить доступ к комнате с помощью корпоративной голосовой связи, чтобы комната могла быть включена с номером телефона, необходимо использовать Skype для бизнеса Online (план 2) с лицензией на телефонную систему или Office 365 (1).</span><span class="sxs-lookup"><span data-stu-id="7b29b-118">To entitle the room with the Enterprise Voice capability so the room can be enabled with a phone number, a Skype for Business Online Plan 2 with the Phone System license or Office 365 E5 is required (1).</span></span>
    
- <span data-ttu-id="7b29b-119">Если вам потребуются возможности телефонного подключения к собранию, вам потребуется позвонить на аудио-и видеоконференции.</span><span class="sxs-lookup"><span data-stu-id="7b29b-119">If you need dial-in capabilities from a meeting, you will need an audio conferencing and Phone System license.</span></span>  <span data-ttu-id="7b29b-120">Если вам требуется возможность исходящих вызовов из собрания, вам потребуется внутренний или внутренний и Международный план звонков.</span><span class="sxs-lookup"><span data-stu-id="7b29b-120">If you need dial-out capabilities from a meeting, you will need a domestic or domestic and international Calling Plan.</span></span> 
    
- <span data-ttu-id="7b29b-121">Для учетной записи комнаты Skype не требуется лицензия на Exchange Online, так как эта учетная запись должна быть настроена как учетная запись почтового ящика ресурса.</span><span class="sxs-lookup"><span data-stu-id="7b29b-121">An Exchange Online license is not required for the Skype Room account because the account should be configured as a resource mailbox account.</span></span>
    
## <a name="provisioning-overview"></a><span data-ttu-id="7b29b-122">Общие сведения о подготовке</span><span class="sxs-lookup"><span data-stu-id="7b29b-122">Provisioning overview</span></span>

<span data-ttu-id="7b29b-123">На следующей схеме представлен обзор процесса подготовки учетной записи системы комнат Skype в Office 365.</span><span class="sxs-lookup"><span data-stu-id="7b29b-123">The following diagram provides an overview of the Skype Room System account provisioning flow in Office 365.</span></span>
  
![Действия по подготовке системы комнат Skype для Office 365](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a><span data-ttu-id="7b29b-125">Определение новой конференц-зала</span><span class="sxs-lookup"><span data-stu-id="7b29b-125">Identify a new conference room</span></span>

<span data-ttu-id="7b29b-126">Возможно, у вас уже есть почтовый ящик помещения ресурсов в Exchange, который предоставляет функцию планирования, или вы можете создать почтовый ящик ресурса, чтобы упростить развертывание системы комнат Skype.</span><span class="sxs-lookup"><span data-stu-id="7b29b-126">You may already have a resource room mailbox in Exchange that provides the scheduling feature, or you may be creating a resource mailbox for the first time to facilitate Skype Room System deployment.</span></span> <span data-ttu-id="7b29b-127">В любом случае необходимо указать учетную запись комнаты, которая будет использоваться в клиенте.</span><span class="sxs-lookup"><span data-stu-id="7b29b-127">In any case, you must identify a room account to be used in your tenant.</span></span> <span data-ttu-id="7b29b-128">В разделах подготовки Exchange Online и Skype для бизнеса представлены рекомендации для обоих типов учетных записей.</span><span class="sxs-lookup"><span data-stu-id="7b29b-128">The Exchange Online Provision and Skype for Business Provision sections provide guidance for both kinds of accounts.</span></span> <span data-ttu-id="7b29b-129">Например, предположим, что у вас есть две следующие комнаты, и вы хотите развернуть систему комнат Skype для обоих из них:</span><span class="sxs-lookup"><span data-stu-id="7b29b-129">For example, let's say you have the following two rooms, and you would like to deploy Skype Room System for both of them:</span></span>
  
- <span data-ttu-id="7b29b-130">Существующая учетная запись почтового ящика ресурса: confrm1@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="7b29b-130">Existing Resource Mailbox Account: confrm1@contoso.onmicrosoft.com</span></span>
    
- <span data-ttu-id="7b29b-131">Новая учетная запись почтового ящика ресурса: confrm2@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="7b29b-131">New Resource Mailbox Account: confrm2@contoso.onmicrosoft.com</span></span>
    
## <a name="exchange-online-provisioning"></a><span data-ttu-id="7b29b-132">Подготовка Exchange Online</span><span class="sxs-lookup"><span data-stu-id="7b29b-132">Exchange Online provisioning</span></span>

<span data-ttu-id="7b29b-133">Сначала подключитесь к Exchange Online PowerShell, выполнив инструкции, приведенные в этом разделе, [подключитесь к Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span><span class="sxs-lookup"><span data-stu-id="7b29b-133">First, connect to Exchange Online PowerShell by following the instructions in the topic, [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
  
<span data-ttu-id="7b29b-134">Чтобы задать существующую учетную запись почтового ящика для комнаты ресурсов для системы комнат Skype, выполните следующие команды в Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="7b29b-134">To set an existing resource room mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:</span></span>
  
```powershell
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

<span data-ttu-id="7b29b-135">Чтобы создать новую учетную запись почтового ящика ресурсов Exchange для системы комнат Skype, выполните следующие команды в Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="7b29b-135">To create a new Exchange resource mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:</span></span>
  
```powershell
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

<span data-ttu-id="7b29b-136">Предыдущие команды настраивают или создают новую учетную запись почтового ящика ресурса Exchange для использования системы комнат Skype, поддерживая учетную запись.</span><span class="sxs-lookup"><span data-stu-id="7b29b-136">The previous commands set up or create a new Exchange resource mailbox account for Skype Room System usage by enabling the account.</span></span>
  
<span data-ttu-id="7b29b-137">После создания почтового ящика можно использовать командлет Set-CalendarProcessing в Exchange Online PowerShell для настройки почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="7b29b-137">After creating the mailbox, you can use the Set-CalendarProcessing cmdlet in Exchange Online PowerShell to configure the mailbox.</span></span> <span data-ttu-id="7b29b-138">Для получения дополнительных сведений обратитесь к разделу 3 – 6 в разделе Локальные развертывания одного леса.</span><span class="sxs-lookup"><span data-stu-id="7b29b-138">Refer to steps 3 through 6 under Single forest on-premises deployments for more details</span></span>

## <a name="assigning-a-skype-for-business-online-license"></a><span data-ttu-id="7b29b-139">Назначение лицензии Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="7b29b-139">Assigning a Skype for Business Online license</span></span>

<span data-ttu-id="7b29b-140">Теперь вы можете назначить лицензию Skype для бизнеса Online (план 2) или Skype для бизнеса Online (план 3) с помощью административного портала Office 365, как описано в статье [назначение и удаление лицензий для Office 365 для бизнеса](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) или в [лицензии на надстройку Skype для бизнеса](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7).</span><span class="sxs-lookup"><span data-stu-id="7b29b-140">Now you can assign a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license by using the Office 365 administrative portal as described in [Assign or remove licenses for Office 365 for business](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) or in [Skype for Business add-on licensing](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7).</span></span> 
  
<span data-ttu-id="7b29b-141">После назначения лицензии для Skype для бизнеса Online вы сможете войти в систему и проверить, активна ли эта учетная запись с помощью любого клиента Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="7b29b-141">After you assign a license for Skype for Business Online, you will be able to log in and validate that the account is active using any Skype for Business client.</span></span>
  
## <a name="skype-for-business-online-provisioning"></a><span data-ttu-id="7b29b-142">Подготовка к работе в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="7b29b-142">Skype for Business Online provisioning</span></span>

<span data-ttu-id="7b29b-143">После создания и включения учетной записи почтового ящика для помещения в ресурс, как показано выше, и лицензирования учетной записи для Skype для бизнеса Online учетная запись будет синхронизироваться с лесом Exchange Online в лесу Skype для бизнеса Online с помощью Лес Windows Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="7b29b-143">After a resource room mailbox account has been created and enabled as shown previously, and you have licensed the account for Skype For Business Online the account will synchronize from the Exchange Online forest to Skype for Business Online forest by using the Windows Azure Active Directory forest.</span></span> <span data-ttu-id="7b29b-144">Для подготовки учетной записи системы комнат Skype в пуле Skype для бизнеса Online необходимо выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="7b29b-144">The following steps are required to provision the Skype Room System account in the Skype for Business Online pool.</span></span> <span data-ttu-id="7b29b-145">Эти действия одинаковы для существующей учетной записи почтового ящика ресурса или только что созданной учетной записи (confrm1 или confrm2), так как после включения в Exchange Online обе эти учетные записи будут синхронизированы с Skype для бизнеса Online аналогичным образом:</span><span class="sxs-lookup"><span data-stu-id="7b29b-145">These steps are the same for both an existing resource mailbox account or a newly created account (confrm1 or confrm2), because once they are enabled in Exchange Online, both of these accounts will be synchronized to Skype for Business Online in the same way:</span></span>
  
1. <span data-ttu-id="7b29b-146">Создайте удаленный сеанс PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7b29b-146">Create a Remote PowerShell session.</span></span> <span data-ttu-id="7b29b-147">Обратите внимание, что вам потребуется скачать модуль соединителя Skype для бизнеса Online и помощник по входу в Microsoft Online Services и проверить, настроен ли компьютер.</span><span class="sxs-lookup"><span data-stu-id="7b29b-147">Note that you will need to download Skype for Business Online Connector Module and Microsoft Online Services Sign-In Assistant and make sure that your computer is configured.</span></span> <span data-ttu-id="7b29b-148">Для получения дополнительных сведений ознакомьтесь со статьей [Настройка компьютера для Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="7b29b-148">For more information, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
    
   ```powershell
   Import-Module LyncOnlineConnector
   $cssess=New-CsOnlineSession -Credential $cred
   Import-PSSession $cssess -AllowClobber
   ```

2. <span data-ttu-id="7b29b-149">Чтобы включить учетную запись системы комнат Skype для Skype для бизнеса, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="7b29b-149">To enable an Skype Room System account for Skype for Business, run the following command:</span></span>
    
   ```powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    <span data-ttu-id="7b29b-150">Вы можете получить адрес RegistrarPool, на котором пользователи Skype для бизнеса находятся из одной из существующих учетных записей, выполнив следующую команду, чтобы возвратить это свойство:</span><span class="sxs-lookup"><span data-stu-id="7b29b-150">You can obtain the RegistrarPool address where your Skype for Business users are homed from one of your existing accounts by using the following command to returns this property:</span></span>
    
   ```powershell
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

>[!NOTE] 
><span data-ttu-id="7b29b-151">Многофакторная проверка подлинности (MFA) не поддерживается для учетных записей системы комнат Skype.</span><span class="sxs-lookup"><span data-stu-id="7b29b-151">Multi-Factor Authentication (MFA) isn't supported for Skype Room System accounts.</span></span> 

## <a name="password-expiration"></a><span data-ttu-id="7b29b-152">Срок действия пароля</span><span class="sxs-lookup"><span data-stu-id="7b29b-152">Password expiration</span></span>

<span data-ttu-id="7b29b-153">В Office 365 политика истечения срока действия паролей по умолчанию для всех учетных записей пользователей составляет 90 дней, если не настроена другая политика истечения срока действия пароля.</span><span class="sxs-lookup"><span data-stu-id="7b29b-153">In Office 365, the default password expiration policy for all of your user accounts is 90 days unless you configure a different password expiration policy.</span></span> <span data-ttu-id="7b29b-154">Для учетных записей системы комнат Skype можно выбрать параметр срок действия пароля не ограничен, выполнив указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="7b29b-154">For Skype Room System accounts, you can select the Password never expires setting with the following steps.</span></span>
  
1. <span data-ttu-id="7b29b-155">Создайте сеанс Windows Azure Active Directory с помощью учетных данных глобального администратора клиента.</span><span class="sxs-lookup"><span data-stu-id="7b29b-155">Create a Windows Azure Active Directory session by using your tenant global administrator credentials.</span></span>
    
    ```powershell
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. <span data-ttu-id="7b29b-156">Для учетной записи комнаты системы комнат Skype, созданной ранее с помощью следующей команды, установите параметр пароль не ограничен сроком действия.</span><span class="sxs-lookup"><span data-stu-id="7b29b-156">Set the Password never expires setting for the Skype Room System room account created previously by using the following command:</span></span>
    
   ```powershell
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

<span data-ttu-id="7b29b-157">Для получения дополнительных сведений ознакомьтесь со статьей [Настройка компьютера для Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="7b29b-157">For more information, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
  
## <a name="validate"></a><span data-ttu-id="7b29b-158">Проверка</span><span class="sxs-lookup"><span data-stu-id="7b29b-158">Validate</span></span>

<span data-ttu-id="7b29b-159">Для проверки подлинности можно использовать любой клиент Skype для бизнеса, чтобы войти в созданную учетную запись.</span><span class="sxs-lookup"><span data-stu-id="7b29b-159">For validation, you should be able to use any Skype for Business client to sign in to the account you created.</span></span>

