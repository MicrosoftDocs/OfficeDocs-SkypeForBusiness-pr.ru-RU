---
title: 'Lync Server 2013: создание потоков обработки вызовов системы интерактивного автоответчика'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Design interactive voice response call flows
ms:assetid: f3477f0a-3ad5-4b13-a73c-046aa451db19
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413020(v=OCS.15)
ms:contentKeyID: 48185826
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 487fa3d4842ad67f3433966a08a889e454450351
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834466"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="design-interactive-voice-response-call-flows-in-lync-server-2013"></a><span data-ttu-id="05248-102">Создание потоков обработки вызовов системы интерактивного автоответчика в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05248-102">Design interactive voice response call flows in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="05248-103">_**Тема последнего изменения:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="05248-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="05248-p101">Интерактивный автоответчик (IVR) используется для получения сведений от вызывающих абонентов и последующего перенаправления в соответствующую очередь. Вы можете указать пары вопросов и ответов, определяющие используемую очередь. В зависимости от ответа вызывающий абонент слышит следующий вопрос или перенаправляется в соответствующую очередь. Вопросы IVR и ответы вызывающего абонента предоставляются отвечающему агенту, когда он или она принимает вызов. Эта система предоставляет агенту ценные сведения.</span><span class="sxs-lookup"><span data-stu-id="05248-p101">You can use interactive voice response (IVR) to obtain information from callers and direct the call to the appropriate queue. Question-and-answer pairs determine which queue to use. Depending on the caller’s response, the caller either hears a follow-up question, or is routed to the appropriate queue. The IVR questions and the caller’s responses are provided to the responding agent who accepts the call, providing valuable information to the agent.</span></span>

<div>

## <a name="overview-of-ivr-features"></a><span data-ttu-id="05248-108">Обзор возможностей интерактивного автоответчика</span><span class="sxs-lookup"><span data-stu-id="05248-108">Overview of IVR Features</span></span>

<span data-ttu-id="05248-109">Приложение "группа ответа" поддерживает распознавание речи и возможности преобразования текста в речь на 26 языках.</span><span class="sxs-lookup"><span data-stu-id="05248-109">The Response Group application offers speech recognition and text-to-speech capabilities in 26 languages.</span></span> <span data-ttu-id="05248-110">Вопросы интерактивного автоответчика вводятся с помощью функции преобразования текста в речь либо из звукового файла Wave (.wav) или Windows Media (.wma).</span><span class="sxs-lookup"><span data-stu-id="05248-110">You can enter IVR questions using text-to-speech or a wave (.wav) or Windows Media audio (.wma) file.</span></span> <span data-ttu-id="05248-111">Вызывающие абоненты могут отвечать голосом или в режиме двухтонального многочастотного набора (DTMF).</span><span class="sxs-lookup"><span data-stu-id="05248-111">Callers can respond by using voice or dual-tone multifrequency (DTMF) responses.</span></span>

<span data-ttu-id="05248-p103">Интерактивные рабочие процессы поддерживают 2 уровня вопросов, каждый из которых имеет до 4 возможных ответов. Интерактивный автоответчик задает звонящему вопрос и в зависимости от ответа звонящего перенаправляет его в очередь или задает второй вопрос, который также имеет до 4 возможных ответов. Звонящий перенаправляется в соответствующую очередь в зависимости от ответа на вопрос второго уровня.</span><span class="sxs-lookup"><span data-stu-id="05248-p103">Interactive workflows support up to two levels of questions, with each question having up to four possible answers. The IVR asks the caller a question, and depending on the caller’s response, routes the caller to a queue or asks a second question. The second question can also have four possible answers. Depending on the answer to the second-level question, the caller is routed to the appropriate queue.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="05248-116">При проектировании потоков звонков с помощью командной консоли Lync Server вы можете определить любые уровни интерактивный АВТООТВЕТЧИКных вопросов и любое количество ответов.</span><span class="sxs-lookup"><span data-stu-id="05248-116">When you design call flows by using Lync Server Management Shell, you can define any number levels of IVR questions and any number of answers.</span></span> <span data-ttu-id="05248-117">However, for caller usability, we recommend that you not use more than three levels of questions, with not more than five answers each.</span><span class="sxs-lookup"><span data-stu-id="05248-117">However, for caller usability, we recommend that you not use more than three levels of questions, with not more than five answers each.</span></span> <span data-ttu-id="05248-118">Кроме того, если вы разработаем потока обзвона с более чем четырьмя вопросами, вы не сможете изменить поток звонков с помощью панели управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="05248-118">In addition, if you design a call flow that has more than two levels of questions with more than four answers each, you cannot edit the call flow by using Lync Server 2013 Control Panel.</span></span>



</div>

<span data-ttu-id="05248-119">Вопросы IVR и ответы вызывающего абонента предоставляются отвечающему агенту, принимающему звонок.</span><span class="sxs-lookup"><span data-stu-id="05248-119">The IVR questions and the caller’s responses are provided to the responding agent who accepts the call.</span></span>

</div>

<div>

## <a name="working-with-speech-technologies"></a><span data-ttu-id="05248-120">Работа с речевыми технологиями</span><span class="sxs-lookup"><span data-stu-id="05248-120">Working with Speech Technologies</span></span>

<span data-ttu-id="05248-121">Речевые технологии, такие как распознавание и синтез речи, могут улучшить работу пользователей и позволить получать доступ к информации более естественно и эффективно.</span><span class="sxs-lookup"><span data-stu-id="05248-121">Speech technologies, such as speech recognition and text-to-speech, can enhance customer experience and let people access information more naturally and effectively.</span></span> <span data-ttu-id="05248-122">Но могут быть ситуации, когда заданный текст или голосовой ответ пользователя распознается неправильно речевой системой.</span><span class="sxs-lookup"><span data-stu-id="05248-122">However, there can be cases where the specified text or the user voice response is not recognized correctly by the speech engine.</span></span> <span data-ttu-id="05248-123">Например, символ "\#" переводится обработчиком преобразования текста в речь как слово "номер".</span><span class="sxs-lookup"><span data-stu-id="05248-123">For example, the "\#" symbol is translated by the text-to-speech engine as the word "number."</span></span> <span data-ttu-id="05248-124">Эту проблему можно устранить следующим способом.</span><span class="sxs-lookup"><span data-stu-id="05248-124">This issue can be mitigated by the following:</span></span>

  - <span data-ttu-id="05248-p106">Речевой модуль предоставляет звонящему пять попыток для ответа на вопрос. Если звонящий неправильно отвечает на вопрос (т. е. ответ не входит в число допустимых ответов) или не отвечает на вопрос, то ему или ей предоставляется еще одна попытка. Звонящему предоставляется 5 попыток, после чего звонок разъединяется. Вы можете настроить IVR для воспроизведения настраиваемого сообщения после каждой ошибки. Вопрос повторяется каждый раз.</span><span class="sxs-lookup"><span data-stu-id="05248-p106">The speech engine gives the caller five attempts to answer the question. If the caller answers the question incorrectly (that is, the answer is not one of the specified responses) or does not provide an answer at all, the caller gets another chance to answer the question. The caller has five attempts to answer the question before being disconnected. You can configure the IVR to play a customized message after each caller error. The question is repeated each time.</span></span>

  - <span data-ttu-id="05248-p107">Чтобы минимизировать возможность интерпретации шума окружающей среды как ответа, используйте более длительные ответы. Например, в ответах должно быть более одного слога и они должны значительно отличаться друг от друга.</span><span class="sxs-lookup"><span data-stu-id="05248-p107">To minimize the potential for ambient noise to be interpreted by the speech engine as a response, use longer responses. For example, responses should have more than one syllable and should sound significantly different from each other.</span></span>

  - <span data-ttu-id="05248-p108">Если ваши вопросы предполагают как речевые, так и тональные (DTMF) ответы, настройте речевые ответы со словами, представляющими концепцию, а не ответы DTMF. Например, вместо "Нажмите или скажите один" используйте "Нажмите 1 или скажите «счета»".</span><span class="sxs-lookup"><span data-stu-id="05248-p108">If your questions have both speech and DTMF responses, configure the speech responses with words that represent the concept rather than the DTMF response. For example, instead of using "Press or say one" use "Press 1 or say billing."</span></span>

  - <span data-ttu-id="05248-134">После настройки IVR, позвоните но номеру, прослушайте голосовые подсказки, ответьте на каждую из них голосом и убедитесь, что IVR звучит и работает, как ожидается.</span><span class="sxs-lookup"><span data-stu-id="05248-134">After you design your IVR, call the workflow, listen to the prompts, respond to each of the prompts using voice, and verify that the IVR sounds and behaves as expected.</span></span> <span data-ttu-id="05248-135">Затем вы можете изменить IVR, чтобы определить проблемы с интерпретацией.</span><span class="sxs-lookup"><span data-stu-id="05248-135">You can then modify the IVR to fix any interpretation issues.</span></span> <span data-ttu-id="05248-136">В предыдущем примере, если вам нужно сослаться на \# ключ, вы можете переписать запрос интерактивный автоответчик, чтобы использовать имя ключа, а не \# символ.</span><span class="sxs-lookup"><span data-stu-id="05248-136">Following the previous example, if you need to refer to the \# key, you can rewrite your IVR prompt to use the key name, rather than the \# symbol.</span></span> <span data-ttu-id="05248-137">Пример: Для связи с сотрудником отдела продаж нажмите кнопку с решеткой.</span><span class="sxs-lookup"><span data-stu-id="05248-137">For example, "To talk to sales, press the pound key."</span></span>

</div>

<div>

## <a name="ivr-design-examples"></a><span data-ttu-id="05248-138">Примеры IVR</span><span class="sxs-lookup"><span data-stu-id="05248-138">IVR Design Examples</span></span>

<span data-ttu-id="05248-139">В следующих разделах представлены примеры различных сценариев IVR и пар вопросов и ответов.</span><span class="sxs-lookup"><span data-stu-id="05248-139">The following sections contain examples of different IVR scenarios and question-and-answer pairs.</span></span>

<div>

## <a name="ivr-with-one-level-of-questions"></a><span data-ttu-id="05248-140">IVR с одним уровнем вопросов</span><span class="sxs-lookup"><span data-stu-id="05248-140">IVR with One Level of Questions</span></span>

<span data-ttu-id="05248-p110">В следующем примере показан IVR, использующий один уровень вопросов. Автоответчик применяет распознавание речи для обнаружения ответа звонящего.</span><span class="sxs-lookup"><span data-stu-id="05248-p110">The following example shows an IVR that uses one level of questions. It uses speech recognition to detect the caller’s response.</span></span>

<span data-ttu-id="05248-p111">**Вопрос:** "Благодарим за звонок в отдел кадров. Для обсуждения заработной платы скажите «зарплата». Для обсуждения других вопросов скажите «кадры»".</span><span class="sxs-lookup"><span data-stu-id="05248-p111">**Question:** "Thank you for calling Human Resources. If you would like to speak to payroll, say payroll. Otherwise, say HR."</span></span>

  - <span data-ttu-id="05248-146">**Выбран вариант 1:** вызывающий абонент перенаправляется в группу, отвечающую за зарплату.</span><span class="sxs-lookup"><span data-stu-id="05248-146">**Option 1 is selected:** The caller is routed to the payroll team.</span></span>

  - <span data-ttu-id="05248-147">**Выбран вариант 2:** вызывающий абонент перенаправляется в группу отдела кадров.</span><span class="sxs-lookup"><span data-stu-id="05248-147">**Option 2 is selected:** The caller is routed to the human resources team.</span></span>

<span data-ttu-id="05248-148">На следующем рисунке показан поток вызовов.</span><span class="sxs-lookup"><span data-stu-id="05248-148">The following figure shows the call flow.</span></span>

<span data-ttu-id="05248-149">**Одноуровневый интерактивный поток вызовов**</span><span class="sxs-lookup"><span data-stu-id="05248-149">**One-level interactive call flow**</span></span>

<span data-ttu-id="05248-150">![Проектирование потоков звонков с помощью интерактивной голосовой РЕСПО] (images/Gg413020.4820a9f7-b5b0-4831-b972-baae0c015ec1(OCS.15).jpg "Проектирование потоков звонков с помощью интерактивной голосовой РЕСПО")</span><span class="sxs-lookup"><span data-stu-id="05248-150">![Design Call Flows by Using Interactive Voice Respo](images/Gg413020.4820a9f7-b5b0-4831-b972-baae0c015ec1(OCS.15).jpg "Design Call Flows by Using Interactive Voice Respo")</span></span>

</div>

<div>

## <a name="ivr-with-two-levels-of-questions"></a><span data-ttu-id="05248-151">IVR с двумя уровнями вопросов</span><span class="sxs-lookup"><span data-stu-id="05248-151">IVR with Two Levels of Questions</span></span>

<span data-ttu-id="05248-p112">В следующем примере показан IVR, использующий два уровня вопросов. Он позволяет звонящим отвечать с использованием речи или команд DTMF.</span><span class="sxs-lookup"><span data-stu-id="05248-p112">The following example shows an IVR that uses two levels of questions. It allows callers to respond using either speech or DTMF keypad input.</span></span>

<span data-ttu-id="05248-p113">**Вопрос:** "Благодарим за звонок в справочную службу отдела информационных технологий. Если неполадка связана с доступом к сети, нажмите 1 или скажите «сеть». Если неполадка связана с программным обеспечением, нажмите 2 или скажите «программное обеспечение». Если неполадка связана с оборудованием, нажмите 3 или скажите «оборудование»".</span><span class="sxs-lookup"><span data-stu-id="05248-p113">**Question:** "Thank you for calling the IT Help Desk. If you have a network access problem, press 1 or say network. If you have a software problem, press 2 or say software. If you have a hardware problem, press 3 or say hardware."</span></span>

  - <span data-ttu-id="05248-158">**Выбран вариант 1:** вызывающий абонент перенаправляется в группу поддержки сети.</span><span class="sxs-lookup"><span data-stu-id="05248-158">**Option 1 is selected:** The caller is routed to the network support team.</span></span>

  - <span data-ttu-id="05248-159">**Выбран вариант 2:** вызывающему абоненту задается следующий вопрос.</span><span class="sxs-lookup"><span data-stu-id="05248-159">**Option 2 is selected:** The caller is asked a follow-up question:</span></span>
    
    <span data-ttu-id="05248-p114">**Вопрос:** "Если неполадка связана с операционной системой, нажмите 1 или скажите «операционная система». Если неполадка связана с внутренним приложением, нажмите 2 или скажите «внутреннее приложение». В случае иных неполадок нажмите 3 или скажите иное".</span><span class="sxs-lookup"><span data-stu-id="05248-p114">**Question:** "If this is an operating system problem, press 1 or say operating system. If this is a problem with an internal application, press 2 or say internal application. Otherwise, press 3 or say other."</span></span>
    
      - <span data-ttu-id="05248-163">**Выбран вариант 1:** вызывающий абонент перенаправляется в группу поддержки операционных систем.</span><span class="sxs-lookup"><span data-stu-id="05248-163">**Option 1 is selected:** The caller is routed to the operating systems support team.</span></span>
    
      - <span data-ttu-id="05248-164">**Выбран вариант 2:** вызывающий абонент перенаправляется в группу поддержки внутренних приложений.</span><span class="sxs-lookup"><span data-stu-id="05248-164">**Option 2 is selected:** The caller is routed to the internal applications support team.</span></span>
    
      - <span data-ttu-id="05248-165">**Выбран вариант 3:** вызывающий абонент перенаправляется в группу поддержки программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="05248-165">**Option 3 is selected:** The caller is routed to the software support team.</span></span>

  - <span data-ttu-id="05248-166">**Выбран вариант 3:** вызывающему абоненту задается следующий вопрос.</span><span class="sxs-lookup"><span data-stu-id="05248-166">**Option 3 is selected:** The caller is asked a follow-up question:</span></span>
    
    <span data-ttu-id="05248-p115">**Вопрос:** "Если неполадка связана с принтером, нажмите 1. В противном случае нажмите 2".</span><span class="sxs-lookup"><span data-stu-id="05248-p115">**Question:** "If this is a printer problem press 1. Otherwise, press 2."</span></span>
    
      - <span data-ttu-id="05248-169">**Выбран вариант 1:** вызывающий абонент перенаправляется в группу поддержки принтеров.</span><span class="sxs-lookup"><span data-stu-id="05248-169">**Option 1 is selected:** The caller is routed to the printer support team.</span></span>
    
      - <span data-ttu-id="05248-170">**Выбран вариант 2:** вызывающий абонент перенаправляется в группу поддержки оборудования.</span><span class="sxs-lookup"><span data-stu-id="05248-170">**Option 2 is selected:** The caller is routed to the hardware support team.</span></span>

<span data-ttu-id="05248-171">На следующем рисунке показан поток вызовов.</span><span class="sxs-lookup"><span data-stu-id="05248-171">The following figure shows the call flow.</span></span>

<span data-ttu-id="05248-172">**Двухуровневый интерактивный поток вызовов**</span><span class="sxs-lookup"><span data-stu-id="05248-172">**Two-level interactive call flow**</span></span>

<span data-ttu-id="05248-173">![Проектирование потоков звонков с помощью интерактивной голосовой РЕСПО] (images/Gg413020.a5b62083-312d-4419-898b-d1a225a5379f(OCS.15).jpg "Проектирование потоков звонков с помощью интерактивной голосовой РЕСПО")</span><span class="sxs-lookup"><span data-stu-id="05248-173">![Design Call Flows by Using Interactive Voice Respo](images/Gg413020.a5b62083-312d-4419-898b-d1a225a5379f(OCS.15).jpg "Design Call Flows by Using Interactive Voice Respo")</span></span>

</div>

</div>

<div>

## <a name="best-practices"></a><span data-ttu-id="05248-174">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="05248-174">Best Practices</span></span>

<span data-ttu-id="05248-175">В следующем списке описываются некоторые рекомендации по созданию IVR.</span><span class="sxs-lookup"><span data-stu-id="05248-175">The following list describes some best practices for designing your IVR:</span></span>

  - <span data-ttu-id="05248-p116">Позвольте звонящему быстро перейти к нужной задаче. Избегайте слишком большого объема информации или длинных маркетинговых сообщений.</span><span class="sxs-lookup"><span data-stu-id="05248-p116">Let the caller get to the task quickly. Avoid providing too much information or lengthy marketing messages in your IVR.</span></span>

  - <span data-ttu-id="05248-p117">Если вы хотите включить длинное сообщение, рассмотрите возможность добавления его к первому вопросу, а не к сообщению приветствия. Звонящие смогут пропустить сообщение, если оно входит в первый вопрос, ответив на него, но они не смогут пропустить приветствие.</span><span class="sxs-lookup"><span data-stu-id="05248-p117">If you want to include a lengthy message, consider appending it to the first question instead of to the welcome message. Callers can bypass the message if it is part of the first question by answering the question, but they cannot bypass the welcome message.</span></span>

  - <span data-ttu-id="05248-p118">Говорите на языке звонящего, избегайте высокопарных фраз, говорите естественно.</span><span class="sxs-lookup"><span data-stu-id="05248-p118">Speak in the caller’s language. Avoid stilted language. Speak naturally.</span></span>

  - <span data-ttu-id="05248-p119">Пишите эффективные подсказки. Удалите все ненужные варианты. Структурируйте информацию так, чтобы ожидаемый ответ звонящего приходился на конце предложения. Например: "Чтобы поговорить с группой продаж, нажмите 1".</span><span class="sxs-lookup"><span data-stu-id="05248-p119">Write efficient and effective prompts. Remove any unnecessary options. Structure the information so that the caller’s expected response is at the end of the sentence. For example, “To speak to the sales team, press 1."</span></span>

  - <span data-ttu-id="05248-p120">Сделайте голосовые ответы понятными для пользователя. Например, если вы указываете и тональные, и голосовые ответы, используйте, например, следующую фразу: "Чтобы поговорить с группой продаж, нажмите 1 или скажите «продажи»".</span><span class="sxs-lookup"><span data-stu-id="05248-p120">Make voice responses user friendly. For example, if you specify both DTMF and voice responses, use something like: "To speak to the sales team, press 1 or say sales."</span></span>

  - <span data-ttu-id="05248-189">Проверьте IVR на группе пользователей перед развертыванием в организации.</span><span class="sxs-lookup"><span data-stu-id="05248-189">Test the IVR on a group of users before you deploy it across your organization.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

