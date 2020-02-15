---
title: 'Lync Server 2013: Использование двухфакторной проверки подлинности с клиентом Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using two-factor authentication with Lync client
ms:assetid: d4136e61-c3ab-4b26-85c8-c1b2c24f5ee3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn338071(v=OCS.15)
ms:contentKeyID: 55115593
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cbd45e3e54ec9fb6b1a9757c0a46a1454901f749
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007458"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-two-factor-authentication-with-lync-client-and-lync-server-2013"></a><span data-ttu-id="11457-102">Применение двухфакторной проверки подлинности с клиентом Lync и Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="11457-102">Using two-factor authentication with Lync client and Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="11457-103">_**Последнее изменение темы:** 2013-07-11_</span><span class="sxs-lookup"><span data-stu-id="11457-103">_**Topic Last Modified:** 2013-07-11_</span></span>

<span data-ttu-id="11457-104">В этом разделе описывается, как использовать преимущества двухфакторной проверки подлинности с клиентом Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="11457-104">This topic described how to take advantage of two-factor authentication with Lync 2013 client.</span></span>

<div>

## <a name="sign-in-to-lync-2013-for-the-first-time"></a><span data-ttu-id="11457-105">Первый вход в Lync 2013</span><span class="sxs-lookup"><span data-stu-id="11457-105">Sign in to Lync 2013 for the first time</span></span>

<span data-ttu-id="11457-106">Данные для входа в Lync обычно настраиваются автоматически при установке Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="11457-106">Your Lync sign-in information is usually configured automatically when Lync 2013 is installed.</span></span> <span data-ttu-id="11457-107">Но при первом использовании Lync может потребоваться запуск клиента вручную.</span><span class="sxs-lookup"><span data-stu-id="11457-107">But the first time you use Lync, you might have to manually start the client.</span></span>

<span data-ttu-id="11457-108">**Вход в Lync в первый раз**</span><span class="sxs-lookup"><span data-stu-id="11457-108">**To sign in to Lync for the first time**</span></span>

1.  <span data-ttu-id="11457-109">Войдите в сеть Организации.</span><span class="sxs-lookup"><span data-stu-id="11457-109">Log on to your organization’s network.</span></span>

2.  <span data-ttu-id="11457-110">Нажмите кнопку **Пуск** \> **все программы** \> **Microsoft \> Lync Lync 2013**.</span><span class="sxs-lookup"><span data-stu-id="11457-110">Select **Start** \> **All Programs** \> **Microsoft Lync \> Lync 2013**.</span></span>
    
    <span data-ttu-id="11457-111">Вы должны увидеть экран входа в Lync.</span><span class="sxs-lookup"><span data-stu-id="11457-111">You should see the Lync sign-in screen.</span></span>
    
      - <span data-ttu-id="11457-112">Если поле адрес для входа уже заполнено, убедитесь, что указан правильный адрес.</span><span class="sxs-lookup"><span data-stu-id="11457-112">If the sign-in address box is already filled in, confirm that the address shown is correct.</span></span>
    
      - <span data-ttu-id="11457-113">Если это не так, или если поле пустое, введите адрес для входа в Lync (как правило, это то же, что и ваш адрес электронной почты).</span><span class="sxs-lookup"><span data-stu-id="11457-113">If it’s not correct, or if the box is empty, enter your Lync sign-in address (this is usually the same as your email address).</span></span>
    
      - <span data-ttu-id="11457-114">Если отображается пустое поле пароля, добавьте пароль.</span><span class="sxs-lookup"><span data-stu-id="11457-114">If an empty password box is displayed, add your password.</span></span>

3.  <span data-ttu-id="11457-115">Нажмите кнопку **войти**.</span><span class="sxs-lookup"><span data-stu-id="11457-115">Select **Sign-in**.</span></span>

</div>

<div>

## <a name="sign-out-of-lync"></a><span data-ttu-id="11457-116">Выход из Lync</span><span class="sxs-lookup"><span data-stu-id="11457-116">Sign out of Lync</span></span>

<span data-ttu-id="11457-117">По завершении работы с Lync можно закрыть экран, выйти из сеанса или выйти из программы в меню файл.</span><span class="sxs-lookup"><span data-stu-id="11457-117">When you’re finished using Lync, you can close the display, sign out of your session, or exit from the program, all from the File menu.</span></span> <span data-ttu-id="11457-118">В следующей таблице приводятся отличия в параметрах.</span><span class="sxs-lookup"><span data-stu-id="11457-118">The following table explains the differences in the options.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="11457-119">Параметр</span><span class="sxs-lookup"><span data-stu-id="11457-119">Option</span></span></th>
<th><span data-ttu-id="11457-120">Действие</span><span class="sxs-lookup"><span data-stu-id="11457-120">What it does</span></span></th>
<th><span data-ttu-id="11457-121">Способ выполнения</span><span class="sxs-lookup"><span data-stu-id="11457-121">How to perform it</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="11457-122">Закрытие</span><span class="sxs-lookup"><span data-stu-id="11457-122">Close</span></span></p></td>
<td><p><span data-ttu-id="11457-123">Закрывает отображение Lync, но позволяет сеансу Lync, указанному с ИДЕНТИФИКАТОРом пользователя, продолжали работать.</span><span class="sxs-lookup"><span data-stu-id="11457-123">Closes your Lync display but lets the Lync session identified with your user ID continue to run.</span></span> <span data-ttu-id="11457-124">Это значит, что вы можете продолжать получать уведомления и взаимодействовать с другими пользователями.</span><span class="sxs-lookup"><span data-stu-id="11457-124">This is so you can continue to get notifications and interact with others.</span></span></p>
<p><span data-ttu-id="11457-125">Вы можете вернуться к экрану в любое время, щелкнув значок Lync на панели задач или в области уведомлений в нижней части экрана.</span><span class="sxs-lookup"><span data-stu-id="11457-125">You can get the display back at any time by clicking the Lync icon on the taskbar or the notification area at the bottom of your screen.</span></span></p></td>
<td><p><span data-ttu-id="11457-126">В главном окне Lync выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="11457-126">On the Lync main window, do one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="11457-127">Нажмите кнопку <strong>Параметры</strong> , а затем нажмите кнопку <strong>Закрыть</strong> <strong>файл</strong> &gt; .</span><span class="sxs-lookup"><span data-stu-id="11457-127">Select the <strong>Options</strong> button, then select <strong>File</strong> &gt; <strong>Close</strong>.</span></span></p></li>
<li><p><span data-ttu-id="11457-128">Нажмите кнопку <strong>Close</strong> (X) (закрыть) в правом верхнем углу окна.</span><span class="sxs-lookup"><span data-stu-id="11457-128">Click the <strong>Close</strong> button (X) in the upper-right corner of the window.</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11457-129">Выход</span><span class="sxs-lookup"><span data-stu-id="11457-129">Sign out</span></span></p></td>
<td><p><span data-ttu-id="11457-130">Завершает сеанс Lync, связанный с ИДЕНТИФИКАТОРом пользователя, но Lync продолжает работать в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="11457-130">Ends the Lync session associated with your user ID, but Lync continues to run in the background.</span></span> <span data-ttu-id="11457-131">После выхода появится окно входа.</span><span class="sxs-lookup"><span data-stu-id="11457-131">When you sign out, the sign-in window will appear.</span></span></p>
<div>

> [!TIP]  
> <span data-ttu-id="11457-132">Выберите <STRONG>удалить мои данные для входа</STRONG> , когда вы выйдете из системы, чтобы удалить запись идентификатора входа и пароля с компьютера.</span><span class="sxs-lookup"><span data-stu-id="11457-132">Select <STRONG>Delete my sign-in information</STRONG> when you sign out to remove the record of your logon ID and password from the computer.</span></span> <span data-ttu-id="11457-133">Это может облегчить пользователям поддержку для устранения неполадок, связанных с входом.</span><span class="sxs-lookup"><span data-stu-id="11457-133">Doing this might make it easier for support people to troubleshoot sign-in issues.</span></span> <span data-ttu-id="11457-134">Кроме того, она может помочь обеспечить более надежную защиту данных, делая неавторизованными для пользователей возможность входа в систему с учетными данными.</span><span class="sxs-lookup"><span data-stu-id="11457-134">It can also help ensure your sign-in information is more secure by making it difficult for unauthorized users to log on with your credentials.</span></span>


</div></td>
<td><p><span data-ttu-id="11457-135">В главном окне Lync нажмите кнопку <strong>Параметры</strong> , а затем выберите команду <strong>выйти из</strong> <strong>файла</strong> &gt; .</span><span class="sxs-lookup"><span data-stu-id="11457-135">On the Lync main window, select the <strong>Options</strong> button, then select <strong>File</strong> &gt; <strong>Sign Out</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11457-136">Выход</span><span class="sxs-lookup"><span data-stu-id="11457-136">Exit</span></span></p></td>
<td><p><span data-ttu-id="11457-137">Завершает сеанс Lync и завершает работу Lync на компьютере.</span><span class="sxs-lookup"><span data-stu-id="11457-137">Ends your Lync session and shuts down Lync on your computer.</span></span> <span data-ttu-id="11457-138">Если вы хотите перезапустить Lync, нажмите кнопку <strong>Пуск</strong> &gt; <strong>все программы</strong> &gt; , <strong>Microsoft Lync</strong> &gt; <strong>Lync 2013</strong>.</span><span class="sxs-lookup"><span data-stu-id="11457-138">After exiting, if you want to restart Lync, select <strong>Start</strong> &gt; <strong>All Programs</strong> &gt; <strong>Microsoft Lync</strong> &gt; <strong>Lync 2013</strong>.</span></span></p></td>
<td><p><span data-ttu-id="11457-139">В главном окне Lync нажмите кнопку <strong>Параметры</strong> , а затем выберите команду <strong>выход из</strong> <strong>файла</strong> &gt; .</span><span class="sxs-lookup"><span data-stu-id="11457-139">On the Lync main window, select the <strong>Options</strong> button, then select <strong>File</strong> &gt; <strong>Exit</strong>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="sign-in-to-lync-with-a-smart-card"></a><span data-ttu-id="11457-140">Вход в Lync со смарт-картой</span><span class="sxs-lookup"><span data-stu-id="11457-140">Sign in to Lync with a Smart Card</span></span>

<span data-ttu-id="11457-141">В некоторых организациях теперь используется многоэтапный процесс входа, называемый двухфакторной проверкой подлинности, чтобы повысить уровень безопасности для пользователей Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="11457-141">Some organizations now use a multi-step sign-in process, called two-factor authentication, to increase security for their Lync 2013 users.</span></span> <span data-ttu-id="11457-142">Если вы предполагаете использовать этот параметр, вам потребуется "смарт-карта", чтобы войти в Lync.</span><span class="sxs-lookup"><span data-stu-id="11457-142">If you’re expected to use this option, you’ll need a “smart card” to sign in to Lync.</span></span> <span data-ttu-id="11457-143">Смарт-карты могут быть двух, физическими и виртуальными:</span><span class="sxs-lookup"><span data-stu-id="11457-143">Smart cards come in two varieties, physical and virtual:</span></span>

  - <span data-ttu-id="11457-144">**Физический**   размер кредитной карты.</span><span class="sxs-lookup"><span data-stu-id="11457-144">**Physical**   About the size of a credit card.</span></span> <span data-ttu-id="11457-145">Вы вставляете его в устройство чтения смарт-карт при входе.</span><span class="sxs-lookup"><span data-stu-id="11457-145">You insert it into a smart card reader when you log in.</span></span>

  - <span data-ttu-id="11457-146">**Виртуальный**   , не являющийся физическим, но электронный идентификатор, который записывается в специальную микросхему компьютера, что в сущности приводит к сборке смарт-карты в компьютере.</span><span class="sxs-lookup"><span data-stu-id="11457-146">**Virtual**   Not a physical object, but an electronic identifier that gets written to a special chip on your computer, which in essence builds the smart card into your computer.</span></span> <span data-ttu-id="11457-147">Доступно только для компьютеров с Windows 8, содержащих микросхему доверенного платформенного модуля (доверенного платформенного модуля).</span><span class="sxs-lookup"><span data-stu-id="11457-147">Available only for use with Windows 8 computers that contain the TPM (Trusted Platform Module) chip.</span></span>

<div>

## <a name="enroll-your-smart-card"></a><span data-ttu-id="11457-148">Регистрация смарт-карты</span><span class="sxs-lookup"><span data-stu-id="11457-148">Enroll your smart card</span></span>

<span data-ttu-id="11457-149">Перед входом в систему с помощью смарт-карты необходимо, чтобы ваши учетные данные пользователя были идентифицированы с помощью карточки.</span><span class="sxs-lookup"><span data-stu-id="11457-149">Before you can sign in with a smart card, the card must be “enrolled”—that is, your user credentials have to be identified with the card.</span></span> <span data-ttu-id="11457-150">В этом случае карта является физической или виртуальной.</span><span class="sxs-lookup"><span data-stu-id="11457-150">This is the case whether the card is physical or virtual.</span></span> <span data-ttu-id="11457-151">Этот процесс может уже выполняться администратором Lync Server.</span><span class="sxs-lookup"><span data-stu-id="11457-151">This process may already been carried out by your Lync Server administrator.</span></span> <span data-ttu-id="11457-152">Если вы не знаете, были ли они выполнены, проверяйте, существуют ли они.</span><span class="sxs-lookup"><span data-stu-id="11457-152">Check with them if you’re not sure whether that has been done.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="11457-153">Так как каждая виртуальная смарт-карта связана только с устройством, на котором она установлена, для каждого используемого компьютера Windows 8 должна быть зарегистрирована отдельная плата.</span><span class="sxs-lookup"><span data-stu-id="11457-153">Since each virtual smart card is associated only with the device it’s installed on, a separate card will need to be enrolled for each Windows 8 computer you use.</span></span>



</div>

<span data-ttu-id="11457-154">**Регистрация смарт-карты вручную**</span><span class="sxs-lookup"><span data-stu-id="11457-154">**To manually enroll your smart card**</span></span>

1.  <span data-ttu-id="11457-155">Войдите на компьютер, на котором будет работать Lync.</span><span class="sxs-lookup"><span data-stu-id="11457-155">Log on to the computer you’ll be running Lync on.</span></span>

2.  <span data-ttu-id="11457-156">С помощью Internet Explorer перейдите на страницу веб-регистрации центра сертификации в Организации.</span><span class="sxs-lookup"><span data-stu-id="11457-156">Using Internet Explorer, browse to your organization’s Certificate Authority Web Enrollment page.</span></span>
    
    <span data-ttu-id="11457-157">Если вы еще не сделали это, обратитесь к администратору Lync Server за веб-адресом этого ресурса.</span><span class="sxs-lookup"><span data-stu-id="11457-157">Ask your Lync Server administrator for the web address of this resource if you don’t already have it.</span></span> <span data-ttu-id="11457-158">URL-адрес будет выглядеть примерно так: https://MyCA.\[йоуркомпанинаме\]. com/certsrv.</span><span class="sxs-lookup"><span data-stu-id="11457-158">The URL will look something like this: https://MyCA.\[yourcompanyname\].com/certsrv.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="11457-159">Если вы используете Internet Explorer 10, вам может потребоваться просмотреть этот веб-сайт в режиме совместимости.</span><span class="sxs-lookup"><span data-stu-id="11457-159">If you’re using Internet Explorer 10, you may need to view this website in Compatibility Mode.</span></span>

    
    </div>

3.  <span data-ttu-id="11457-160">Когда вам будет предложено войти на страницу сертификации, выполните вход в систему, используя учетную запись домена (а не администратора компьютера).</span><span class="sxs-lookup"><span data-stu-id="11457-160">When you’re prompted to log on to the certification page, log on using your domain account (rather than as administrator of your computer).</span></span>

4.  <span data-ttu-id="11457-161">На странице приветствия веб-сайта выберите **запросить сертификат**.</span><span class="sxs-lookup"><span data-stu-id="11457-161">On the website Welcome Page, select **Request a certificate**.</span></span>

5.  <span data-ttu-id="11457-162">Выберите **Расширенный запрос**.</span><span class="sxs-lookup"><span data-stu-id="11457-162">Select **Advanced Request**.</span></span>

6.  <span data-ttu-id="11457-163">Выберите **создать и отправить запрос к этому ЦС**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="11457-163">Select **Create and submit a request to this CA**, then click **Next**.</span></span>

7.  <span data-ttu-id="11457-164">Теперь вы увидите страницу с названием станции регистрации смарт-карт.</span><span class="sxs-lookup"><span data-stu-id="11457-164">Now you’ll see a page called Smart Card Enrollment Station.</span></span> <span data-ttu-id="11457-165">Утвердите запрос на установку элемента управления ActiveX, а затем заполните форму Расширенный запрос сертификата следующим образом:</span><span class="sxs-lookup"><span data-stu-id="11457-165">Approve the request to install the ActiveX control, and then complete the Advanced Certificate Request form as follows:</span></span>
    
    1.  <span data-ttu-id="11457-166">В раскрывающемся списке **шаблон сертификата** выберите пункт **пользователь смарт-карты** .</span><span class="sxs-lookup"><span data-stu-id="11457-166">Select **Smartcard user** from the **Certificate Template** dropdown list.</span></span>
    
    2.  <span data-ttu-id="11457-167">Выберите **создать новый набор ключей**.</span><span class="sxs-lookup"><span data-stu-id="11457-167">Select **Create new key set**.</span></span>
    
    3.  <span data-ttu-id="11457-168">Найдите информацию о производителе на метке смарт-карты и выберите ее в раскрывающемся списке **CSP** .</span><span class="sxs-lookup"><span data-stu-id="11457-168">Find the manufacturer information on the label of your smart card and select that manufacturer from the **CSP** dropdown list.</span></span>
    
    4.  <span data-ttu-id="11457-169">Выберите в качестве формата запроса **CSP** , если он еще не выбран.</span><span class="sxs-lookup"><span data-stu-id="11457-169">Select **CSP** as the Request Format, if it’s not already selected.</span></span>
    
    5.  <span data-ttu-id="11457-170">Выберите **SHA1** из раскрывающегося списка алгоритм хеширования, если он еще не выбран.</span><span class="sxs-lookup"><span data-stu-id="11457-170">Select **sha1** from the Hash Algorithm dropdown list, if it’s not already selected.</span></span>
    
    6.  <span data-ttu-id="11457-171">Присвойте сертификату имя, которое вы будете распознать, и нажмите кнопку **Отправить**.</span><span class="sxs-lookup"><span data-stu-id="11457-171">Give your certificate a name you’ll recognize, and click **Submit**.</span></span>

8.  <span data-ttu-id="11457-172">Теперь вставьте пустую смарт-карту в устройство чтения карт, подключенное к станции регистрации, и нажмите кнопку **зарегистрировать**.</span><span class="sxs-lookup"><span data-stu-id="11457-172">Now insert your blank smart card into the card reader attached to the enrollment station and click **Enroll**.</span></span>

9.  <span data-ttu-id="11457-173">При появлении соответствующего запроса введите персональный идентификационный номер (ПИН-код) и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="11457-173">When prompted, enter your personal identification number (PIN), and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="11457-174">Если сотрудник службы технической поддержки не предоставил вам специальный ПИН-код для регистрации смарт-карты, используйте значение ПИН-кода смарт-карты по умолчанию 12345678.</span><span class="sxs-lookup"><span data-stu-id="11457-174">If your technical support person has not given you a special PIN to use to enroll your smart card, use the default smart card PIN value, which is 12345678.</span></span>

    
    </div>

10. <span data-ttu-id="11457-175">Выберите параметр для принудительного изменения ПИН-кода при первом использовании смарт-карты.</span><span class="sxs-lookup"><span data-stu-id="11457-175">Select the option to force the user (you) to change the PIN the first time the smart card is used.</span></span>

11. <span data-ttu-id="11457-176">Теперь вставьте пустую смарт-карту в устройство чтения карт, подключенное к станции регистрации, и нажмите кнопку **зарегистрировать**.</span><span class="sxs-lookup"><span data-stu-id="11457-176">Now insert your blank smart card into the card reader attached to the enrollment station and click **Enroll**.</span></span>

12. <span data-ttu-id="11457-177">При появлении соответствующего запроса введите персональный идентификационный номер (ПИН-код) и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="11457-177">When prompted, enter your personal identification number (PIN), and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="11457-178">Если сотрудник службы технической поддержки не предоставил вам специальный ПИН-код для регистрации смарт-карты, используйте значение ПИН-кода смарт-карты по умолчанию 12345678.</span><span class="sxs-lookup"><span data-stu-id="11457-178">If your technical support person has not given you a special PIN to use to enroll your smart card, use the default smart card PIN value, which is 12345678.</span></span>

    
    </div>

13. <span data-ttu-id="11457-179">Выберите параметр для принудительного изменения ПИН-кода при первом использовании смарт-карты.</span><span class="sxs-lookup"><span data-stu-id="11457-179">Select the option to force the user (you) to change the PIN the first time the smart card is used.</span></span>

14. <span data-ttu-id="11457-180">Нажмите кнопку **ОК** , чтобы подтвердить, что на отображаемом сертификате есть ваши сведения.</span><span class="sxs-lookup"><span data-stu-id="11457-180">Click **OK** to confirm that the certificate displayed has your information on it.</span></span>

15. <span data-ttu-id="11457-181">Когда появится уведомление о том, что сертификат выдан, щелкните **установить этот сертификат** для завершения процедуры регистрации.</span><span class="sxs-lookup"><span data-stu-id="11457-181">Once you see the notice that the certificate has been issued, click **Install this certificate** to complete the enrollment process.</span></span>

</div>

<div>

## <a name="sign-in-to-lync-with-your-smart-card-credentials"></a><span data-ttu-id="11457-182">Вход в Lync с использованием учетных данных смарт-карты</span><span class="sxs-lookup"><span data-stu-id="11457-182">Sign in to Lync with your smart card credentials</span></span>

<span data-ttu-id="11457-183">Перед первым использованием смарт-карты рекомендуется нажать кнопку **удалить мои данные для входа** на странице входа в Lync.</span><span class="sxs-lookup"><span data-stu-id="11457-183">Before you use your smart card for the first time, it’s recommended that you click **Delete my sign-in info** on the Lync sign-in page.</span></span> <span data-ttu-id="11457-184">При этом удаляются все учетные данные для входа, хранящиеся на компьютере, и исключается возможный источник ошибки.</span><span class="sxs-lookup"><span data-stu-id="11457-184">Doing this clears any sign-in credentials stored on your computer, and eliminates a possible source of error.</span></span>

<span data-ttu-id="11457-185">**Вход в Lync с использованием учетных данных смарт-карты**</span><span class="sxs-lookup"><span data-stu-id="11457-185">**To sign in to Lync with your smart card credentials**</span></span>

1.  <span data-ttu-id="11457-186">Запустите клиент Lync.</span><span class="sxs-lookup"><span data-stu-id="11457-186">Start the Lync client.</span></span>

2.  <span data-ttu-id="11457-187">На экране входа в поле **адрес** для входа введите имя учетной записи пользователя для входа и нажмите кнопку **войти**.</span><span class="sxs-lookup"><span data-stu-id="11457-187">On the Sign in screen, type your sign in user account name in the **Sign-in address** box, and then click **Sign In**.</span></span>

3.  <span data-ttu-id="11457-188">Если вы используете виртуальную смарт-карту, пропустите этот шаг.</span><span class="sxs-lookup"><span data-stu-id="11457-188">If you are using a virtual smart card, skip this step.</span></span>
    
    <span data-ttu-id="11457-189">Если вы используете физическую смарт-карту, вставьте смарт-карту в устройство чтения смарт-карт и выводите приглашение, а затем нажмите кнопку **ОК** при обнаружении карточки.</span><span class="sxs-lookup"><span data-stu-id="11457-189">If you are using a physical smart card, insert the smart card into your smart card reader and prompted to do so, and then click **OK** when the card is detected.</span></span>

4.  <span data-ttu-id="11457-190">Введите PIN-код для смарт-карты и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="11457-190">Type in the PIN number you for your smart card and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="11457-191">Если вы не назначили свой ПИН-код смарт-карты специалистом службы поддержки, используйте значение по умолчанию — 12345678.</span><span class="sxs-lookup"><span data-stu-id="11457-191">If you were not assigned a smart card PIN number by your support person, use the default value, which is 12345678.</span></span>

    
    </div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

