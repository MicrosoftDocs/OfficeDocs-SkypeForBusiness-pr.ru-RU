---
title: Управление двухфакторной проверкой подлинности в Skype для бизнеса Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 16f08710-8961-4659-acbf-ebb95a198fb4
description: 'Сводка: Управление двухфакторной проверки подлинности в Скайп для Business Server 2015.'
ms.openlocfilehash: c72e998b7e12993f328aa4e331c67d5b660e94aa
ms.sourcegitcommit: a5b8b0a1e5ae5eb718e296ca6df6687368ee9174
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2018
ms.locfileid: "19504518"
---
# <a name="manage-two-factor-authentication-in-skype-for-business-server-2015"></a><span data-ttu-id="677b6-103">Управление двухфакторной проверкой подлинности в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="677b6-103">Manage two-factor authentication in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="677b6-104">**Сводка:** Управление двухфакторной проверки подлинности в Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="677b6-104">**Summary:** Manage two-factor authentication in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="677b6-105">Двухфакторная проверка подлинности обеспечивает повышенную безопасность и требует от пользователей использования двух критериев проверки подлинности: сочетания пароля и имени пользователя и маркер или сертификата.</span><span class="sxs-lookup"><span data-stu-id="677b6-105">Two-factor authentication provides improved security by requiring users to provide two forms of authentication or identification, namely a user name/password combination and a token or certificate.</span></span> <span data-ttu-id="677b6-106">Это также называется «то, что у вас есть то, что вы знаете.»</span><span class="sxs-lookup"><span data-stu-id="677b6-106">This is also known as "something you have, something you know."</span></span> 
  
<span data-ttu-id="677b6-p102">Типичным примером двухфакторной проверки подлинности с помощью сертификата может послужить использование смарт-карт. Смарт-карта включает в себя сертификат, связанный с учетной записью пользователя, и проверяется с помощью информации о пользователе и сертификате, хранящейся на сервере. Сервер сравнивает информацию о пользователе (имя пользователя и пароль) с представленным сертификатом, в результате чего происходит проверка учетных данных и определяется подлинность пользователя.</span><span class="sxs-lookup"><span data-stu-id="677b6-p102">A typical example of two-factor authentication with a certificate is the use of smart cards. A smart card contains a certificate associated with the user account, and can be validated against user and certificate information stored on a server. By comparing the user information (user name and password) to the certificate provided, the server validates the credentials and authenticates the user.</span></span>
  
<span data-ttu-id="677b6-110">При настройке Скайп для среды Business Server 2015 для поддержки двухфакторной проверки подлинности необходимо учитывайте следующие темы.</span><span class="sxs-lookup"><span data-stu-id="677b6-110">Consider the following subjects when configuring a Skype for Business Server 2015 environment to support two-factor authentication.</span></span>
  
## <a name="client-support"></a><span data-ttu-id="677b6-111">Поддержка клиента</span><span class="sxs-lookup"><span data-stu-id="677b6-111">Client Support</span></span>

<span data-ttu-id="677b6-112">Накопительные пакеты обновления для Lync Server 2013: июля 2013 г. для настольных компьютеров и Скайп для клиента Business — только клиентов, которые в настоящее время поддерживают двухфакторной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="677b6-112">The Cumulative Updates for Lync Server 2013: July 2013 desktop client and the Skype for Business client are the only clients that currently support two-factor authentication.</span></span>
  
## <a name="topology-requirements"></a><span data-ttu-id="677b6-113">Требования к топологии</span><span class="sxs-lookup"><span data-stu-id="677b6-113">Topology Requirements</span></span>

<span data-ttu-id="677b6-114">Клиенты, настоятельно рекомендуется развернуть двухфакторной проверки подлинности с помощью выделенного Скайп Business Server 2015 с пограничного сервера, директоров и пулов пользователей.</span><span class="sxs-lookup"><span data-stu-id="677b6-114">Customers are strongly encouraged to deploy two-factor authentication using dedicated Skype for Business Server 2015 with Edge, Director, and User Pools.</span></span> <span data-ttu-id="677b6-115">Для включения пассивной проверки подлинности для пользователей Lync необходимо отключить другие способы проверки подлинности для других ролей и служб, включая:</span><span class="sxs-lookup"><span data-stu-id="677b6-115">To enable passive authentication for users, other authentication methods must be disabled for other roles and services, including the following:</span></span>
  
|<span data-ttu-id="677b6-116">**Тип настройки**</span><span class="sxs-lookup"><span data-stu-id="677b6-116">**Configuration Type**</span></span>|<span data-ttu-id="677b6-117">**Тип службы**</span><span class="sxs-lookup"><span data-stu-id="677b6-117">**Service Type**</span></span>|<span data-ttu-id="677b6-118">**Роль сервера**</span><span class="sxs-lookup"><span data-stu-id="677b6-118">**Server Role**</span></span>|<span data-ttu-id="677b6-119">**Тип проверки подлинности для отключения**</span><span class="sxs-lookup"><span data-stu-id="677b6-119">**Authentication Type to Disable**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="677b6-120">Веб-служба</span><span class="sxs-lookup"><span data-stu-id="677b6-120">Web Service</span></span>  <br/> |<span data-ttu-id="677b6-121">Веб-сервера</span><span class="sxs-lookup"><span data-stu-id="677b6-121">WebServer</span></span>  <br/> |<span data-ttu-id="677b6-122">Директор</span><span class="sxs-lookup"><span data-stu-id="677b6-122">Director</span></span>  <br/> |<span data-ttu-id="677b6-123">Kerberos, NTLM и сертификат</span><span class="sxs-lookup"><span data-stu-id="677b6-123">Kerberos, NTLM, and Certificate</span></span>  <br/> |
|<span data-ttu-id="677b6-124">Веб-служба</span><span class="sxs-lookup"><span data-stu-id="677b6-124">Web Service</span></span>  <br/> |<span data-ttu-id="677b6-125">Веб-сервера</span><span class="sxs-lookup"><span data-stu-id="677b6-125">WebServer</span></span>  <br/> |<span data-ttu-id="677b6-126">Сервер переднего плана</span><span class="sxs-lookup"><span data-stu-id="677b6-126">Front End</span></span>  <br/> |<span data-ttu-id="677b6-127">Kerberos, NTLM и сертификат</span><span class="sxs-lookup"><span data-stu-id="677b6-127">Kerberos, NTLM, and Certificate</span></span>  <br/> |
|<span data-ttu-id="677b6-128">Прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="677b6-128">Proxy</span></span>  <br/> |<span data-ttu-id="677b6-129">EdgeServer</span><span class="sxs-lookup"><span data-stu-id="677b6-129">EdgeServer</span></span>  <br/> |<span data-ttu-id="677b6-130">Пограничный</span><span class="sxs-lookup"><span data-stu-id="677b6-130">Edge</span></span>  <br/> |<span data-ttu-id="677b6-131">Kerberos и NTLM</span><span class="sxs-lookup"><span data-stu-id="677b6-131">Kerberos and NTLM</span></span>  <br/> |
|<span data-ttu-id="677b6-132">Прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="677b6-132">Proxy</span></span>  <br/> |<span data-ttu-id="677b6-133">Регистратор</span><span class="sxs-lookup"><span data-stu-id="677b6-133">Registrar</span></span>  <br/> |<span data-ttu-id="677b6-134">Сервер переднего плана</span><span class="sxs-lookup"><span data-stu-id="677b6-134">Front End</span></span>  <br/> |<span data-ttu-id="677b6-135">Kerberos и NTLM</span><span class="sxs-lookup"><span data-stu-id="677b6-135">Kerberos and NTLM</span></span>  <br/> |
   
<span data-ttu-id="677b6-136">Пока эти типы проверки подлинности не будут отключены на уровне служб, все другие версии клиента не смогут выполнить успешный вход, поскольку в пределах вашего развертывания включена двухфакторная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="677b6-136">Unless these authentication types are disabled at the service level, all other versions of the client will be unable to sign in successfully once two-factor authentication is enabled within in your deployment.</span></span>
  
## <a name="skype-for-business-service-discovery"></a><span data-ttu-id="677b6-137">Обнаружение служб Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="677b6-137">Skype for Business Service Discovery</span></span>

<span data-ttu-id="677b6-138">DNS-записи, используемые с внутренним и внешним клиентам обнаруживать Скайп для бизнес-служб должны быть настроены для разрешения Скайп для Business server, который не включен для двухфакторной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="677b6-138">DNS records used by internal and/or external clients to discover Skype for Business services should be configured to resolve to a Skype for Business server that is not enabled for two-factor authentication.</span></span> <span data-ttu-id="677b6-139">При такой конфигурации пользователей из Скайп для бизнеса пулов, которые не включены для двухфакторной проверки подлинности не должен будет ввести ПИН-код для проверки подлинности, хотя пользователи из Скайп для бизнеса пулов, доступных для двухфакторной проверки подлинности необходимо ввести свой ПИН-код для проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="677b6-139">With this configuration, users from Skype for Business Pools that are not enabled for two-factor authentication will not be required to enter a PIN to authenticate, while users from Skype for Business Pools that are enabled for two-factor authentication will be required to enter their PIN to authenticate.</span></span>
  
## <a name="exchange-authentication"></a><span data-ttu-id="677b6-140">Проверка подлинности Exchange</span><span class="sxs-lookup"><span data-stu-id="677b6-140">Exchange Authentication</span></span>

<span data-ttu-id="677b6-141">Клиенты, у которых развернут двухфакторной проверки подлинности для Microsoft Exchange может оказаться, что некоторые компоненты в клиенте становятся недоступными.</span><span class="sxs-lookup"><span data-stu-id="677b6-141">Customers who have deployed two-factor authentication for Microsoft Exchange may find that certain features in the client are unavailable.</span></span> <span data-ttu-id="677b6-142">Это происходит в настоящее время разработки, как Скайп для клиента Business не поддерживает двухфакторной проверки подлинности для функции, зависящие от интеграции с Exchange.</span><span class="sxs-lookup"><span data-stu-id="677b6-142">This is currently by design, as the Skype for Business client does not support two-factor authentication for features that are dependent on Exchange integration.</span></span>
  
## <a name="contacts"></a><span data-ttu-id="677b6-143">Контакты</span><span class="sxs-lookup"><span data-stu-id="677b6-143">Contacts</span></span>

<span data-ttu-id="677b6-144">Найти Скайп бизнес-пользователям, настроенных для использования компонента единого хранилища контактов, что свои контакты становятся недоступными после входа в систему с двухфакторной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="677b6-144">Skype for Business users who are configured to leverage the Unified Contact Store feature will find that their contacts are no longer available after signing in with two-factor authentication.</span></span>
  
<span data-ttu-id="677b6-145">Командлет **Invoke-CsUcsRollback** следует использовать для удаления существующего пользователя контактов из единого хранилища контактов и хранить их в Скайп для Business Server 2015 перед включением двухфакторной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="677b6-145">You should use the **Invoke-CsUcsRollback** cmdlet to remove existing user contacts from the Unified Contact Store and store them in Skype for Business Server 2015 before enabling two-factor authentication.</span></span>
  
## <a name="skill-search"></a><span data-ttu-id="677b6-146">Поиск по навыкам</span><span class="sxs-lookup"><span data-stu-id="677b6-146">Skill Search</span></span>

<span data-ttu-id="677b6-147">Пользователи, которые настроены функцию поиск по навыкам в их Скайп для бизнес-среде находятся, что эта функция не работает, если Скайп для бизнеса включен для двухфакторной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="677b6-147">Customers who have configured the Skill Search feature in their Skype for Business environment will find that this feature does not work when Skype for Business is enabled for two-factor authentication.</span></span> <span data-ttu-id="677b6-148">Это объясняется тем, что Microsoft SharePoint не поддерживает двухфакторную проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="677b6-148">This is by design, as Microsoft SharePoint does not currently support two-factor authentication.</span></span>
  
## <a name="credentials"></a><span data-ttu-id="677b6-149">Учетные данные</span><span class="sxs-lookup"><span data-stu-id="677b6-149">Credentials</span></span>

<span data-ttu-id="677b6-150">Существует ряд вопросы развертывания, включающие использование сохраненных Скайп для бизнеса учетные данные, которые могут повлиять на пользователей, которые настроены на использование двухфакторной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="677b6-150">There are a number of deployment considerations involving saved Skype for Business credentials which may impact users who are configured to use two-factor authentication.</span></span>
  
### <a name="deleting-saved-credentials"></a><span data-ttu-id="677b6-151">Удаление сохраненных учетных данных</span><span class="sxs-lookup"><span data-stu-id="677b6-151">Deleting Saved Credentials</span></span>

<span data-ttu-id="677b6-152">Пользователи должны использовать параметр **Удалить Мои сведения входа** в Скайп для клиента Business и удалите их папки профилей SIP от %localappdata%\Microsoft\Office\15.0\Skype для бизнеса, прежде чем для входа в первый раз, с помощью двухфакторной Проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="677b6-152">Users should use the **Delete my sign-in info** option in the Skype for Business client and delete their SIP profile folder from %localappdata%\Microsoft\Office\15.0\Skype for Business before attempting to sign for the first time using two-factor authentication.</span></span>
  
### <a name="disablentcredentials"></a><span data-ttu-id="677b6-153">DisableNTCredentials</span><span class="sxs-lookup"><span data-stu-id="677b6-153">DisableNTCredentials</span></span>

<span data-ttu-id="677b6-154">С помощью метода проверки подлинности Kerberos или NTLM учетные данные пользователя Windows, автоматически используются для проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="677b6-154">With the Kerberos or NTLM authentication method, the user's Windows credentials are used automatically for authentication.</span></span> <span data-ttu-id="677b6-155">В типичных Скайп для развертывания Business Server 2015, где включен Kerberos или NTLM для проверки подлинности пользователей не должно быть введите свои учетные данные при каждом выполняют вход в.</span><span class="sxs-lookup"><span data-stu-id="677b6-155">In a typical Skype for Business Server 2015 deployment where Kerberos and/or NTLM is enabled for authentication, users should not have to enter their credentials every time that they sign in.</span></span>
  
<span data-ttu-id="677b6-156">Если у пользователя запрашиваются учетные данные перед появлением запроса ПИН-кода, на клиентском компьютере мог быть случайно настроен раздел реестра **DisableNTCredentials** (возможно, через групповую политику).</span><span class="sxs-lookup"><span data-stu-id="677b6-156">If users are unintentionally prompted for credentials before they are prompted to enter their PIN, the **DisableNTCredentials** registry key may be unintentionally configured on client computers, possibly through Group Policy.</span></span>
  
<span data-ttu-id="677b6-157">Чтобы избежать дополнительных запрос учетных данных, создайте следующую запись реестра на локальном компьютере или использование Скайп для бизнеса административных шаблонов для применения ко всем пользователям для данного пула, с помощью групповой политики:</span><span class="sxs-lookup"><span data-stu-id="677b6-157">To prevent the additional prompt for credentials, create the following registry entry on the local workstation or use the Skype for Business administrative template to apply to all users for a given pool using Group Policy:</span></span>
  
    HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Office\15.0\Lync
  
    REG_DWORD: DisableNTCredentials
  
    Value: 0x0
  
### <a name="savepassword"></a><span data-ttu-id="677b6-158">SavePassword</span><span class="sxs-lookup"><span data-stu-id="677b6-158">SavePassword</span></span>

<span data-ttu-id="677b6-159">При входе пользователя в систему Скайп для бизнеса в первый раз, пользователю предлагается сохранить свой пароль.</span><span class="sxs-lookup"><span data-stu-id="677b6-159">When a user signs in to Skype for Business for the first time, the user is prompted to save his or her password.</span></span> <span data-ttu-id="677b6-160">Если выбрано, этот параметр позволяет сертификата клиента будут храниться в хранилище личных сертификатов и учетные данные пользователя Windows будут сохраняться в диспетчере учетных данных на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="677b6-160">If selected, this option allows the user's client certificate to be stored in the personal certificate store and the user's Windows credentials to be stored in the Credential Manager of the local computer.</span></span>
  
<span data-ttu-id="677b6-161">Параметр реестра **SavePassword** должны быть отключены во Скайп для бизнеса настроена поддержка двухфакторной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="677b6-161">The **SavePassword** registry setting should be disabled when Skype for Business is configured to support two-factor authentication.</span></span> <span data-ttu-id="677b6-162">Чтобы запретить пользователям сохранять свои пароли, измените следующий параметр реестра на локальном компьютере или использование Скайп для бизнеса административных шаблонов для применения ко всем пользователям для данного пула, с помощью групповой политики:</span><span class="sxs-lookup"><span data-stu-id="677b6-162">To prevent users from saving their passwords, change the following registry entry on the local workstation or use the Skype for Business administrative template to apply to all users for a given pool using Group Policy:</span></span>
  
    HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync
  
    REG_DWORD: SavePassword
  
    Value: 0x0
  
## <a name="ad-fs-20-token-replay"></a><span data-ttu-id="677b6-163">Повтор маркера AD FS 2.0</span><span class="sxs-lookup"><span data-stu-id="677b6-163">AD FS 2.0 Token Replay</span></span>

<span data-ttu-id="677b6-p110">AD FS 2.0 обеспечивает функцию обнаружения повтора маркера, которая позволяет обнаружить и отменить ряд запросов, использующих один маркер. Эта функция поддерживает целостность запросов проверки подлинности в пассивном профиле федерации веб-служб и профиле SAML WebSSO, не позволяя использовать один маркер несколько раз.</span><span class="sxs-lookup"><span data-stu-id="677b6-p110">AD FS 2.0 provides a feature referred to as token replay detection, by which multiple token requests using the same token can be detected and then discarded. When this feature is enabled, token replay detection protects the integrity of authentication requests in both the WS-Federation passive profile and the SAML WebSSO profile by making sure that the same token is never used more than once.</span></span>
  
<span data-ttu-id="677b6-166">Функция обнаружения повтора маркера необходима в особо опасных условиях, например в интерактивных терминалах.</span><span class="sxs-lookup"><span data-stu-id="677b6-166">This feature should be enabled in situations where security is a very high concern such as when using kiosks.</span></span> <span data-ttu-id="677b6-167">Дополнительные сведения об обнаружении повтора видеть [Советы и рекомендации для безопасного планирования и развертывания AD FS 2.0](https://go.microsoft.com/fwlink/p/?LinkId=309215).</span><span class="sxs-lookup"><span data-stu-id="677b6-167">For more information about token replay detection, see [Best Practices for Secure Planning and Deployment of AD FS 2.0](https://go.microsoft.com/fwlink/p/?LinkId=309215).</span></span>
  
## <a name="external-user-access"></a><span data-ttu-id="677b6-168">Доступ внешнего пользователя</span><span class="sxs-lookup"><span data-stu-id="677b6-168">External User Access</span></span>

<span data-ttu-id="677b6-169">Настройка прокси-сервера службы федерации Active Directory или обратный прокси-сервер для поддержки Скайп для бизнеса двухфакторной проверки подлинности из внешних сетей не рассматриваются в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="677b6-169">Configuring an ADFS Proxy or Reverse Proxy to support Skype for Business two-factor authentication from external networks is not covered in these topics.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="677b6-170">См. также</span><span class="sxs-lookup"><span data-stu-id="677b6-170">See also</span></span>

[<span data-ttu-id="677b6-171">Настройка двухфакторной проверки подлинности в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="677b6-171">Configure two-factor authentication in Skype for Business Server 2015</span></span>](configure.md)
  
[<span data-ttu-id="677b6-172">Настройка двухфакторной проверки подлинности в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="677b6-172">Configure two-factor authentication in Skype for Business Server 2015</span></span>](configure.md)