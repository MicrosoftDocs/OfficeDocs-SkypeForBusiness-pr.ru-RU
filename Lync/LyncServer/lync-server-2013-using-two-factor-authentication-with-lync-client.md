---
title: 'Lync Server 2013: Использование двухфакторной проверки подлинности в клиенте Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using two-factor authentication with Lync client
ms:assetid: d4136e61-c3ab-4b26-85c8-c1b2c24f5ee3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn338071(v=OCS.15)
ms:contentKeyID: 55115593
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5af9e9b5268fd218bfe5856473124514cfe34945
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849206"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-two-factor-authentication-with-lync-client-and-lync-server-2013"></a><span data-ttu-id="436ee-102">Использование двухфакторной проверки подлинности в клиенте Lync и Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="436ee-102">Using two-factor authentication with Lync client and Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="436ee-103">_**Тема последнего изменения:** 2013-07-11_</span><span class="sxs-lookup"><span data-stu-id="436ee-103">_**Topic Last Modified:** 2013-07-11_</span></span>

<span data-ttu-id="436ee-104">В этой статье описано, как использовать преимущества двухфакторной проверки подлинности в клиенте Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="436ee-104">This topic described how to take advantage of two-factor authentication with Lync 2013 client.</span></span>

<div>

## <a name="sign-in-to-lync-2013-for-the-first-time"></a><span data-ttu-id="436ee-105">Первый вход в Lync 2013</span><span class="sxs-lookup"><span data-stu-id="436ee-105">Sign in to Lync 2013 for the first time</span></span>

<span data-ttu-id="436ee-106">Данные для входа в Lync обычно настраиваются автоматически при установке Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="436ee-106">Your Lync sign-in information is usually configured automatically when Lync 2013 is installed.</span></span> <span data-ttu-id="436ee-107">Но в первый раз при использовании Lync вам может потребоваться запустить клиент вручную.</span><span class="sxs-lookup"><span data-stu-id="436ee-107">But the first time you use Lync, you might have to manually start the client.</span></span>

<span data-ttu-id="436ee-108">**Первый вход в Lync**</span><span class="sxs-lookup"><span data-stu-id="436ee-108">**To sign in to Lync for the first time**</span></span>

1.  <span data-ttu-id="436ee-109">Войдите в сеть организации.</span><span class="sxs-lookup"><span data-stu-id="436ee-109">Log on to your organization’s network.</span></span>

2.  <span data-ttu-id="436ee-110">Нажмите кнопку **запустить** \> **все программы** \> **, \> Microsoft Lync Lync 2013**.</span><span class="sxs-lookup"><span data-stu-id="436ee-110">Select **Start** \> **All Programs** \> **Microsoft Lync \> Lync 2013**.</span></span>
    
    <span data-ttu-id="436ee-111">Вы увидите экран входа в Lync.</span><span class="sxs-lookup"><span data-stu-id="436ee-111">You should see the Lync sign-in screen.</span></span>
    
      - <span data-ttu-id="436ee-112">Если поле адреса уже заполнено, проверьте правильность адреса.</span><span class="sxs-lookup"><span data-stu-id="436ee-112">If the sign-in address box is already filled in, confirm that the address shown is correct.</span></span>
    
      - <span data-ttu-id="436ee-113">Если это значение неверно или поле пусто, введите адрес для входа в Lync (обычно это то же самое, что и адрес электронной почты).</span><span class="sxs-lookup"><span data-stu-id="436ee-113">If it’s not correct, or if the box is empty, enter your Lync sign-in address (this is usually the same as your email address).</span></span>
    
      - <span data-ttu-id="436ee-114">Если на экране отображается пустое поле пароля, введите свой пароль.</span><span class="sxs-lookup"><span data-stu-id="436ee-114">If an empty password box is displayed, add your password.</span></span>

3.  <span data-ttu-id="436ee-115">Выберите **Вход**.</span><span class="sxs-lookup"><span data-stu-id="436ee-115">Select **Sign-in**.</span></span>

</div>

<div>

## <a name="sign-out-of-lync"></a><span data-ttu-id="436ee-116">Выход из Lync</span><span class="sxs-lookup"><span data-stu-id="436ee-116">Sign out of Lync</span></span>

<span data-ttu-id="436ee-117">Когда вы закончите работу с Lync, вы можете закрыть экран, выйти из сеанса или выйти из программы в меню "файл".</span><span class="sxs-lookup"><span data-stu-id="436ee-117">When you’re finished using Lync, you can close the display, sign out of your session, or exit from the program, all from the File menu.</span></span> <span data-ttu-id="436ee-118">В следующей таблице поясняются различия между этими действиями.</span><span class="sxs-lookup"><span data-stu-id="436ee-118">The following table explains the differences in the options.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="436ee-119">Действие</span><span class="sxs-lookup"><span data-stu-id="436ee-119">Option</span></span></th>
<th><span data-ttu-id="436ee-120">Суть</span><span class="sxs-lookup"><span data-stu-id="436ee-120">What it does</span></span></th>
<th><span data-ttu-id="436ee-121">Порядок выполнения</span><span class="sxs-lookup"><span data-stu-id="436ee-121">How to perform it</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="436ee-122">Закрытие</span><span class="sxs-lookup"><span data-stu-id="436ee-122">Close</span></span></p></td>
<td><p><span data-ttu-id="436ee-123">Закрытие экрана Lync, но с помощью сеанса Lync, определенного для идентификатора пользователя, будет выполняться.</span><span class="sxs-lookup"><span data-stu-id="436ee-123">Closes your Lync display but lets the Lync session identified with your user ID continue to run.</span></span> <span data-ttu-id="436ee-124">Это позволяет по-прежнему получать оповещения и взаимодействовать с другими пользователями.</span><span class="sxs-lookup"><span data-stu-id="436ee-124">This is so you can continue to get notifications and interact with others.</span></span></p>
<p><span data-ttu-id="436ee-125">Вы можете в любое время вернуть экран, щелкнув значок Lync на панели задач или в области уведомлений в нижней части экрана.</span><span class="sxs-lookup"><span data-stu-id="436ee-125">You can get the display back at any time by clicking the Lync icon on the taskbar or the notification area at the bottom of your screen.</span></span></p></td>
<td><p><span data-ttu-id="436ee-126">В главном окне Lync выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="436ee-126">On the Lync main window, do one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="436ee-127">Нажмите кнопку <strong>"Параметры</strong> ", а затем выберите пункт <strong>Закрыть</strong> <strong>файл</strong> &gt; .</span><span class="sxs-lookup"><span data-stu-id="436ee-127">Select the <strong>Options</strong> button, then select <strong>File</strong> &gt; <strong>Close</strong>.</span></span></p></li>
<li><p><span data-ttu-id="436ee-128">Нажмите кнопку <strong>закрытия</strong> (X) в правом верхнем углу окна.</span><span class="sxs-lookup"><span data-stu-id="436ee-128">Click the <strong>Close</strong> button (X) in the upper-right corner of the window.</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="436ee-129">Выйти</span><span class="sxs-lookup"><span data-stu-id="436ee-129">Sign out</span></span></p></td>
<td><p><span data-ttu-id="436ee-130">Завершает сеанс Lync, связанный с вашим ИДЕНТИФИКАТОРом пользователя, но Lync продолжает работать в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="436ee-130">Ends the Lync session associated with your user ID, but Lync continues to run in the background.</span></span> <span data-ttu-id="436ee-131">После выхода на экране отображается окно входа.</span><span class="sxs-lookup"><span data-stu-id="436ee-131">When you sign out, the sign-in window will appear.</span></span></p>
<div>

> [!TIP]  
> <span data-ttu-id="436ee-p105">Если при выходе из требуется удалить с компьютера запись идентификатора и пароля для входа, выберите режим <STRONG>удаления данных для входа</STRONG>. Это упрощает работу сотрудников службы поддержки по устранению неполадок со входом. Кроме того, повышается уровень защиты данных для входа: несанкционированный вход по этим учетным данным затрудняется.</span><span class="sxs-lookup"><span data-stu-id="436ee-p105">Select <STRONG>Delete my sign-in information</STRONG> when you sign out to remove the record of your logon ID and password from the computer. Doing this might make it easier for support people to troubleshoot sign-in issues. It can also help ensure your sign-in information is more secure by making it difficult for unauthorized users to log on with your credentials.</span></span>


</div></td>
<td><p><span data-ttu-id="436ee-135">В главном окне Lync нажмите кнопку <strong>Параметры</strong> , а затем выберите пункт <strong>выход из</strong> <strong>файла</strong> &gt; .</span><span class="sxs-lookup"><span data-stu-id="436ee-135">On the Lync main window, select the <strong>Options</strong> button, then select <strong>File</strong> &gt; <strong>Sign Out</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="436ee-136">Выход</span><span class="sxs-lookup"><span data-stu-id="436ee-136">Exit</span></span></p></td>
<td><p><span data-ttu-id="436ee-137">Завершает сеанс Lync и завершает работу Lync на компьютере.</span><span class="sxs-lookup"><span data-stu-id="436ee-137">Ends your Lync session and shuts down Lync on your computer.</span></span> <span data-ttu-id="436ee-138">Если вы хотите перезапустить Lync, нажмите кнопку <strong>запустить</strong> &gt; <strong>все программы</strong> &gt; , <strong>Microsoft Lync</strong> &gt; <strong>Lync 2013</strong>.</span><span class="sxs-lookup"><span data-stu-id="436ee-138">After exiting, if you want to restart Lync, select <strong>Start</strong> &gt; <strong>All Programs</strong> &gt; <strong>Microsoft Lync</strong> &gt; <strong>Lync 2013</strong>.</span></span></p></td>
<td><p><span data-ttu-id="436ee-139">В главном окне Lync нажмите кнопку <strong>Параметры</strong> , а затем выберите пункт <strong>выход из</strong> <strong>файла</strong> &gt; .</span><span class="sxs-lookup"><span data-stu-id="436ee-139">On the Lync main window, select the <strong>Options</strong> button, then select <strong>File</strong> &gt; <strong>Exit</strong>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="sign-in-to-lync-with-a-smart-card"></a><span data-ttu-id="436ee-140">Вход в Lync с помощью смарт-карты</span><span class="sxs-lookup"><span data-stu-id="436ee-140">Sign in to Lync with a Smart Card</span></span>

<span data-ttu-id="436ee-141">В некоторых организациях теперь для пользователей Lync 2013 используется многоэтапный вход в систему, называемый двухфакторной проверкой подлинности.</span><span class="sxs-lookup"><span data-stu-id="436ee-141">Some organizations now use a multi-step sign-in process, called two-factor authentication, to increase security for their Lync 2013 users.</span></span> <span data-ttu-id="436ee-142">Если вы предполагаете использовать этот параметр, для входа в Lync вам понадобится "смарт-карта".</span><span class="sxs-lookup"><span data-stu-id="436ee-142">If you’re expected to use this option, you’ll need a “smart card” to sign in to Lync.</span></span> <span data-ttu-id="436ee-143">Смарт-карты бывают двух видов, физических и виртуальных.</span><span class="sxs-lookup"><span data-stu-id="436ee-143">Smart cards come in two varieties, physical and virtual:</span></span>

  - <span data-ttu-id="436ee-144">**Физическая**   информация о размере кредитной карты.</span><span class="sxs-lookup"><span data-stu-id="436ee-144">**Physical**   About the size of a credit card.</span></span> <span data-ttu-id="436ee-145">При входе вставляется в устройство чтения смарт-карт.</span><span class="sxs-lookup"><span data-stu-id="436ee-145">You insert it into a smart card reader when you log in.</span></span>

  - <span data-ttu-id="436ee-146">**Виртуальная**   не физическая, но электронный идентификатор, который записывается в специальную микросхему вашего компьютера, что на самом сути создает смарт-карту на компьютере.</span><span class="sxs-lookup"><span data-stu-id="436ee-146">**Virtual**   Not a physical object, but an electronic identifier that gets written to a special chip on your computer, which in essence builds the smart card into your computer.</span></span> <span data-ttu-id="436ee-147">Доступно только для компьютеров с Windows 8, которые содержат микросхему TPM (доверенный платформенный модуль).</span><span class="sxs-lookup"><span data-stu-id="436ee-147">Available only for use with Windows 8 computers that contain the TPM (Trusted Platform Module) chip.</span></span>

<div>

## <a name="enroll-your-smart-card"></a><span data-ttu-id="436ee-148">Регистрация смарт-карты</span><span class="sxs-lookup"><span data-stu-id="436ee-148">Enroll your smart card</span></span>

<span data-ttu-id="436ee-149">Перед первым входом по смарт-карте ее необходимо зарегистрировать, то есть сопоставить с ней учетные данные пользователя.</span><span class="sxs-lookup"><span data-stu-id="436ee-149">Before you can sign in with a smart card, the card must be “enrolled”—that is, your user credentials have to be identified with the card.</span></span> <span data-ttu-id="436ee-150">Это относится как к физической, так и к виртуальной карте.</span><span class="sxs-lookup"><span data-stu-id="436ee-150">This is the case whether the card is physical or virtual.</span></span> <span data-ttu-id="436ee-151">Этот процесс может быть уже выполнен администратором Lync Server.</span><span class="sxs-lookup"><span data-stu-id="436ee-151">This process may already been carried out by your Lync Server administrator.</span></span> <span data-ttu-id="436ee-152">В случае сомнений обратитесь к нему.</span><span class="sxs-lookup"><span data-stu-id="436ee-152">Check with them if you’re not sure whether that has been done.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="436ee-153">Так как каждая виртуальная смарт-карта связана только с устройством, на котором она установлена, для каждого используемого компьютера с Windows 8 необходимо зарегистрировать отдельную карту.</span><span class="sxs-lookup"><span data-stu-id="436ee-153">Since each virtual smart card is associated only with the device it’s installed on, a separate card will need to be enrolled for each Windows 8 computer you use.</span></span>



</div>

<span data-ttu-id="436ee-154">**Регистрация смарт-карты вручную**</span><span class="sxs-lookup"><span data-stu-id="436ee-154">**To manually enroll your smart card**</span></span>

1.  <span data-ttu-id="436ee-155">Войдите в систему на компьютере, на котором будет запущено приложение Lync.</span><span class="sxs-lookup"><span data-stu-id="436ee-155">Log on to the computer you’ll be running Lync on.</span></span>

2.  <span data-ttu-id="436ee-156">В браузере Internet Explorer откройте страницу регистрации сертификатов через Интернет вашей организации.</span><span class="sxs-lookup"><span data-stu-id="436ee-156">Using Internet Explorer, browse to your organization’s Certificate Authority Web Enrollment page.</span></span>
    
    <span data-ttu-id="436ee-157">Попросите администратора Lync Server сделать веб-адрес этого ресурса, если у вас его еще нет.</span><span class="sxs-lookup"><span data-stu-id="436ee-157">Ask your Lync Server administrator for the web address of this resource if you don’t already have it.</span></span> <span data-ttu-id="436ee-158">URL-адрес будет выглядеть примерно так: https://MyCA.\[йоуркомпанинаме\]. com/certsrv.</span><span class="sxs-lookup"><span data-stu-id="436ee-158">The URL will look something like this: https://MyCA.\[yourcompanyname\].com/certsrv.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="436ee-159">Если вы используете Internet Explorer 10, возможно, этот сайт потребуется открыть в режиме совместимости.</span><span class="sxs-lookup"><span data-stu-id="436ee-159">If you’re using Internet Explorer 10, you may need to view this website in Compatibility Mode.</span></span>

    
    </div>

3.  <span data-ttu-id="436ee-160">На странице сертификации войдите со своей учетной записью в домене (а не с учетной записью администратора своего компьютера).</span><span class="sxs-lookup"><span data-stu-id="436ee-160">When you’re prompted to log on to the certification page, log on using your domain account (rather than as administrator of your computer).</span></span>

4.  <span data-ttu-id="436ee-161">На странице приветствия на веб-сайте выберите **Запросить сертификат**.</span><span class="sxs-lookup"><span data-stu-id="436ee-161">On the website Welcome Page, select **Request a certificate**.</span></span>

5.  <span data-ttu-id="436ee-162">Выберите **Расширенный запрос**.</span><span class="sxs-lookup"><span data-stu-id="436ee-162">Select **Advanced Request**.</span></span>

6.  <span data-ttu-id="436ee-163">Выберите **Создать и выдать запрос к этому ЦС**, затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="436ee-163">Select **Create and submit a request to this CA**, then click **Next**.</span></span>

7.  <span data-ttu-id="436ee-164">На экране появится страница "Станция подачи заявок смарт-карт".</span><span class="sxs-lookup"><span data-stu-id="436ee-164">Now you’ll see a page called Smart Card Enrollment Station.</span></span> <span data-ttu-id="436ee-165">Согласитесь на установку элемента ActiveX и заполните форму расширенного запроса сертификата, указав приведенные ниже данные.</span><span class="sxs-lookup"><span data-stu-id="436ee-165">Approve the request to install the ActiveX control, and then complete the Advanced Certificate Request form as follows:</span></span>
    
    1.  <span data-ttu-id="436ee-166">В раскрывающемся списке **Шаблон сертификата** выберите **Пользователь смарт-карты**.</span><span class="sxs-lookup"><span data-stu-id="436ee-166">Select **Smartcard user** from the **Certificate Template** dropdown list.</span></span>
    
    2.  <span data-ttu-id="436ee-167">Выберите **Создать новый набор ключей**.</span><span class="sxs-lookup"><span data-stu-id="436ee-167">Select **Create new key set**.</span></span>
    
    3.  <span data-ttu-id="436ee-168">Найдите сведения об изготовителе на этикетке смарт-карты и выберите этого изготовителя в раскрывающемся списке **Поставщик служб шифрования**.</span><span class="sxs-lookup"><span data-stu-id="436ee-168">Find the manufacturer information on the label of your smart card and select that manufacturer from the **CSP** dropdown list.</span></span>
    
    4.  <span data-ttu-id="436ee-169">В качестве формата запроса выберите **Поставщик служб шифрования**, если этот вариант еще не выбран.</span><span class="sxs-lookup"><span data-stu-id="436ee-169">Select **CSP** as the Request Format, if it’s not already selected.</span></span>
    
    5.  <span data-ttu-id="436ee-170">В раскрывающемся списке "алгоритм хэширования" выберите **sha1**, если этот вариант еще не выбран.</span><span class="sxs-lookup"><span data-stu-id="436ee-170">Select **sha1** from the Hash Algorithm dropdown list, if it’s not already selected.</span></span>
    
    6.  <span data-ttu-id="436ee-171">Присвойте сертификату имя, позволяющее распознавать его, и нажмите кнопку **Отправить**.</span><span class="sxs-lookup"><span data-stu-id="436ee-171">Give your certificate a name you’ll recognize, and click **Submit**.</span></span>

8.  <span data-ttu-id="436ee-172">Теперь вставьте пустую смарт-карту в устройство чтения карт, подсоединенное к станции регистрации, и нажмите кнопку **Заявка**.</span><span class="sxs-lookup"><span data-stu-id="436ee-172">Now insert your blank smart card into the card reader attached to the enrollment station and click **Enroll**.</span></span>

9.  <span data-ttu-id="436ee-173">По запросу введите личный идентификационный номер (PIN‑код, затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="436ee-173">When prompted, enter your personal identification number (PIN), and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="436ee-174">Если специалист службы поддержки не предоставил вам личный ПИН-код для регистрации смарт-карты, используйте значение ПИН-кода по умолчанию: 12345678.</span><span class="sxs-lookup"><span data-stu-id="436ee-174">If your technical support person has not given you a special PIN to use to enroll your smart card, use the default smart card PIN value, which is 12345678.</span></span>

    
    </div>

10. <span data-ttu-id="436ee-175">Активируйте параметр принудительной смены пользователем (вами) ПИН-кода при первом использовании смарт-карты.</span><span class="sxs-lookup"><span data-stu-id="436ee-175">Select the option to force the user (you) to change the PIN the first time the smart card is used.</span></span>

11. <span data-ttu-id="436ee-176">Теперь вставьте пустую смарт-карту в устройство чтения карт, подсоединенное к станции регистрации, и нажмите кнопку **Заявка**.</span><span class="sxs-lookup"><span data-stu-id="436ee-176">Now insert your blank smart card into the card reader attached to the enrollment station and click **Enroll**.</span></span>

12. <span data-ttu-id="436ee-177">По запросу введите личный идентификационный номер (PIN‑код, затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="436ee-177">When prompted, enter your personal identification number (PIN), and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="436ee-178">Если специалист службы поддержки не предоставил вам личный ПИН-код для регистрации смарт-карты, используйте значение ПИН-кода по умолчанию: 12345678.</span><span class="sxs-lookup"><span data-stu-id="436ee-178">If your technical support person has not given you a special PIN to use to enroll your smart card, use the default smart card PIN value, which is 12345678.</span></span>

    
    </div>

13. <span data-ttu-id="436ee-179">Активируйте параметр принудительной смены пользователем (вами) ПИН-кода при первом использовании смарт-карты.</span><span class="sxs-lookup"><span data-stu-id="436ee-179">Select the option to force the user (you) to change the PIN the first time the smart card is used.</span></span>

14. <span data-ttu-id="436ee-180">Нажмите кнопку **ОК** для подтверждения сведений, отображаемых в сертификате.</span><span class="sxs-lookup"><span data-stu-id="436ee-180">Click **OK** to confirm that the certificate displayed has your information on it.</span></span>

15. <span data-ttu-id="436ee-181">При появлении уведомления о выдаче сертификата нажмите кнопку **Установить этот сертификат** для завершения процедуры регистрации.</span><span class="sxs-lookup"><span data-stu-id="436ee-181">Once you see the notice that the certificate has been issued, click **Install this certificate** to complete the enrollment process.</span></span>

</div>

<div>

## <a name="sign-in-to-lync-with-your-smart-card-credentials"></a><span data-ttu-id="436ee-182">Вход в Lync с помощью учетных данных смарт-карты</span><span class="sxs-lookup"><span data-stu-id="436ee-182">Sign in to Lync with your smart card credentials</span></span>

<span data-ttu-id="436ee-183">Прежде чем использовать смарт-карту в первый раз, рекомендуется нажать кнопку **удалить мои данные для входа** на странице входа в Lync.</span><span class="sxs-lookup"><span data-stu-id="436ee-183">Before you use your smart card for the first time, it’s recommended that you click **Delete my sign-in info** on the Lync sign-in page.</span></span> <span data-ttu-id="436ee-184">При этом удаляются хранящиеся на компьютере учетные данные для входа, которые могут служить причиной ошибок.</span><span class="sxs-lookup"><span data-stu-id="436ee-184">Doing this clears any sign-in credentials stored on your computer, and eliminates a possible source of error.</span></span>

<span data-ttu-id="436ee-185">**Вход в Lync с помощью учетных данных смарт-карты**</span><span class="sxs-lookup"><span data-stu-id="436ee-185">**To sign in to Lync with your smart card credentials**</span></span>

1.  <span data-ttu-id="436ee-186">Запустите клиент Lync.</span><span class="sxs-lookup"><span data-stu-id="436ee-186">Start the Lync client.</span></span>

2.  <span data-ttu-id="436ee-187">На экране входа введите имя учетной записи пользователя для входа в поле **Адрес для входа**, затем нажмите кнопку **Вход**.</span><span class="sxs-lookup"><span data-stu-id="436ee-187">On the Sign in screen, type your sign in user account name in the **Sign-in address** box, and then click **Sign In**.</span></span>

3.  <span data-ttu-id="436ee-188">Если вы используете виртуальную смарт-карту, пропустите этот этап.</span><span class="sxs-lookup"><span data-stu-id="436ee-188">If you are using a virtual smart card, skip this step.</span></span>
    
    <span data-ttu-id="436ee-189">В случае физической смарт-карты вставьте ее по запросу в устройство чтения смарт-карт и после обнаружения карты нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="436ee-189">If you are using a physical smart card, insert the smart card into your smart card reader and prompted to do so, and then click **OK** when the card is detected.</span></span>

4.  <span data-ttu-id="436ee-190">Введите PIN‑код смарт-карты,затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="436ee-190">Type in the PIN number you for your smart card and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="436ee-191">Если специалист службы поддержки не предоставил вам ПИН-код для смарт-карты, введите значение по умолчанию: 12345678.</span><span class="sxs-lookup"><span data-stu-id="436ee-191">If you were not assigned a smart card PIN number by your support person, use the default value, which is 12345678.</span></span>

    
    </div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

