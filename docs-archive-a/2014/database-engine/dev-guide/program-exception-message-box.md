---
title: Caixa de mensagem de exceção do programa | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
helpviewer_keywords:
- exception message box [SQL Server]
- displaying exception message box
ms.assetid: c771985b-149c-459a-b3cb-7b15fde01150
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 9d49bdf8c73f86b2c334018d40510b4ae67c85ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685261"
---
# <a name="program-exception-message-box"></a><span data-ttu-id="e30d4-102">Programar caixa de mensagem de exceção</span><span class="sxs-lookup"><span data-stu-id="e30d4-102">Program Exception Message Box</span></span>
  <span data-ttu-id="e30d4-103">Você pode usar a caixa de mensagem de exceção nos aplicativos para proporcionar um controle mais significativo da experiência em mensagens do que a oferecida pela classe <xref:System.Windows.Forms.MessageBox>.</span><span class="sxs-lookup"><span data-stu-id="e30d4-103">You can use the exception message box in your applications to provide significantly more control over the messaging experience than is provided by the <xref:System.Windows.Forms.MessageBox> class.</span></span> <span data-ttu-id="e30d4-104">Para obter mais informações, consulte a [programação da caixa de mensagem de exceção](../../../2014/database-engine/dev-guide/exception-message-box-programming.md).</span><span class="sxs-lookup"><span data-stu-id="e30d4-104">For more information, see [Exception Message Box Programming](../../../2014/database-engine/dev-guide/exception-message-box-programming.md).</span></span> <span data-ttu-id="e30d4-105">Consulte mais informações sobre como obter e implantar o .dll da caixa de mensagem de exceção em [Deploying an Exception Message Box Application](../../../2014/database-engine/dev-guide/deploying-an-exception-message-box-application.md).</span><span class="sxs-lookup"><span data-stu-id="e30d4-105">For information about how to obtain and deploy the exception message box .dll, see [Deploying an Exception Message Box Application](../../../2014/database-engine/dev-guide/deploying-an-exception-message-box-application.md).</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="e30d4-106">Procedimento</span><span class="sxs-lookup"><span data-stu-id="e30d4-106">Procedure</span></span>  
  
#### <a name="to-handle-an-exception-by-using-the-exception-message-box"></a><span data-ttu-id="e30d4-107">Para tratar de uma exceção usando a caixa de mensagem de exceção</span><span class="sxs-lookup"><span data-stu-id="e30d4-107">To handle an exception by using the exception message box</span></span>  
  
1.  <span data-ttu-id="e30d4-108">Adicione uma referência em seu projeto de código gerenciado ao assembly Microsoft.ExceptionMessageBox.dll.</span><span class="sxs-lookup"><span data-stu-id="e30d4-108">Add a reference in your managed code project to the Microsoft.ExceptionMessageBox.dll assembly.</span></span>  
  
2.  <span data-ttu-id="e30d4-109">Adicional Adicione uma `using` diretiva (C#) ou `Imports` ( [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic .net) para usar o <xref:Microsoft.SqlServer.MessageBox> namespace.</span><span class="sxs-lookup"><span data-stu-id="e30d4-109">(Optional) Add a `using` (C#) or `Imports` ([!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic .NET) directive to use the <xref:Microsoft.SqlServer.MessageBox> namespace.</span></span>  
  
3.  <span data-ttu-id="e30d4-110">Crie um bloco try-catch para tratar da exceção antecipada.</span><span class="sxs-lookup"><span data-stu-id="e30d4-110">Create a try-catch block to handle the anticipated exception.</span></span>  
  
4.  <span data-ttu-id="e30d4-111">Dentro do bloco `catch`, crie uma instância da classe <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox>.</span><span class="sxs-lookup"><span data-stu-id="e30d4-111">Within the `catch` block, create an instance of the <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox> class.</span></span> <span data-ttu-id="e30d4-112">Passe o <xref:System.Exception> objeto manipulado pelo `try` - `catch` bloco.</span><span class="sxs-lookup"><span data-stu-id="e30d4-112">Pass the <xref:System.Exception> object handled by the `try`-`catch` block.</span></span>  
  
5.  <span data-ttu-id="e30d4-113">(Opcional) Defina uma ou mais das propriedades de segurança a seguir em <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox>:</span><span class="sxs-lookup"><span data-stu-id="e30d4-113">(Optional) Set one or more of the following properties on <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox>:</span></span>  
  
    -   <span data-ttu-id="e30d4-114"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Buttons%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons>Enumeração que especifica os botões a serem exibidos na caixa de mensagem de exceção.</span><span class="sxs-lookup"><span data-stu-id="e30d4-114"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Buttons%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons> enumeration that specifies the buttons to display in the exception message box.</span></span>  
  
    -   <span data-ttu-id="e30d4-115"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.DefaultButton%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxDefaultButton>Enumeração que especifica o botão padrão para a caixa de mensagem de exceção.</span><span class="sxs-lookup"><span data-stu-id="e30d4-115"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.DefaultButton%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxDefaultButton> enumeration that specifies the default button for the exception message box.</span></span>  
  
    -   <span data-ttu-id="e30d4-116"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Options%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxOptions>Enumeração que você usa para controlar outros comportamentos da caixa de mensagem de exceção.</span><span class="sxs-lookup"><span data-stu-id="e30d4-116"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Options%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxOptions> enumeration that you use to control other behaviors of the exception message box.</span></span>  
  
    -   <span data-ttu-id="e30d4-117"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Symbol%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxSymbol>Enumeração que especifica o símbolo a ser exibido na caixa de mensagem de exceção.</span><span class="sxs-lookup"><span data-stu-id="e30d4-117"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Symbol%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxSymbol> enumeration that specifies the symbol to display in the exception message box.</span></span>  
  
6.  <span data-ttu-id="e30d4-118">Chame o método <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Show%2A> .</span><span class="sxs-lookup"><span data-stu-id="e30d4-118">Call the <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Show%2A> method.</span></span> <span data-ttu-id="e30d4-119">Passe a janela pai à qual pertence a caixa de mensagem de exceção.</span><span class="sxs-lookup"><span data-stu-id="e30d4-119">Pass the parent window to which the exception message box belongs.</span></span>  
  
7.  <span data-ttu-id="e30d4-120">Adicional Observe o valor da <xref:System.Windows.Forms.DialogResult> enumeração retornada se você precisar determinar em qual botão o usuário clicou.</span><span class="sxs-lookup"><span data-stu-id="e30d4-120">(Optional) Note the value of returned <xref:System.Windows.Forms.DialogResult> enumeration if you need to determine which button the user clicked.</span></span>  
  
#### <a name="to-display-the-exception-message-box-without-an-exception"></a><span data-ttu-id="e30d4-121">Para exibir a caixa de mensagem de exceção sem uma exceção</span><span class="sxs-lookup"><span data-stu-id="e30d4-121">To display the exception message box without an exception</span></span>  
  
1.  <span data-ttu-id="e30d4-122">Adicione uma referência em seu projeto de código gerenciado ao assembly Microsoft.ExceptionMessageBox.dll.</span><span class="sxs-lookup"><span data-stu-id="e30d4-122">Add a reference in your managed code project to the Microsoft.ExceptionMessageBox.dll assembly.</span></span>  
  
2.  <span data-ttu-id="e30d4-123">Adicional Adicione uma `using` diretiva (C#) ou `Imports` (Visual Basic .net) para usar o <xref:Microsoft.SqlServer.MessageBox> namespace.</span><span class="sxs-lookup"><span data-stu-id="e30d4-123">(Optional) Add a `using` (C#) or `Imports` (Visual Basic .NET) directive to use the <xref:Microsoft.SqlServer.MessageBox> namespace.</span></span>  
  
3.  <span data-ttu-id="e30d4-124">Criar uma instância da classe <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox>.</span><span class="sxs-lookup"><span data-stu-id="e30d4-124">Create an instance of the <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox> class.</span></span> <span data-ttu-id="e30d4-125">Passe o texto da mensagem como um valor <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="e30d4-125">Pass the message text as a <xref:System.String> value.</span></span>  
  
4.  <span data-ttu-id="e30d4-126">(Opcional) Defina uma ou mais das propriedades de segurança a seguir em <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox>:</span><span class="sxs-lookup"><span data-stu-id="e30d4-126">(Optional) Set one or more of the following properties on <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox>:</span></span>  
  
    -   <span data-ttu-id="e30d4-127"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Buttons%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons>Enumeração que especifica os botões a serem exibidos na caixa de mensagem de exceção.</span><span class="sxs-lookup"><span data-stu-id="e30d4-127"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Buttons%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons> enumeration that specifies the buttons to display in the exception message box.</span></span>  
  
    -   <span data-ttu-id="e30d4-128"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Caption%2A>- legenda da caixa de diálogo da caixa de mensagem de exceção.</span><span class="sxs-lookup"><span data-stu-id="e30d4-128"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Caption%2A> - Dialog box caption of the exception message box.</span></span>  
  
    -   <span data-ttu-id="e30d4-129"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.DefaultButton%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxDefaultButton>Enumeração que especifica o botão padrão para a caixa de diálogo da caixa de mensagem de exceção.</span><span class="sxs-lookup"><span data-stu-id="e30d4-129"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.DefaultButton%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxDefaultButton> enumeration that specifies the default button for the dialog box of the exception message box.</span></span>  
  
    -   <span data-ttu-id="e30d4-130"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Options%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxOptions>Enumeração que você usa para controlar outros comportamentos da caixa de mensagem de exceção.</span><span class="sxs-lookup"><span data-stu-id="e30d4-130"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Options%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxOptions> enumeration that you use to control other behaviors of the exception message box.</span></span>  
  
    -   <span data-ttu-id="e30d4-131"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Symbol%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxSymbol>Enumeração que especifica o símbolo a ser exibido na caixa de mensagem de exceção.</span><span class="sxs-lookup"><span data-stu-id="e30d4-131"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Symbol%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxSymbol> enumeration that specifies the symbol to display in the exception message box.</span></span>  
  
5.  <span data-ttu-id="e30d4-132">Chame o método <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Show%2A> .</span><span class="sxs-lookup"><span data-stu-id="e30d4-132">Call the <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Show%2A> method.</span></span> <span data-ttu-id="e30d4-133">Passe a janela pai à qual pertence a caixa de mensagem de exceção.</span><span class="sxs-lookup"><span data-stu-id="e30d4-133">Pass the parent window to which the exception message box belongs.</span></span>  
  
6.  <span data-ttu-id="e30d4-134">(Opcional) Observe o valor da enumeração <xref:System.Windows.Forms.DialogResult> retornada se precisar determinar em qual botão o usuário clicou.</span><span class="sxs-lookup"><span data-stu-id="e30d4-134">(Optional) Note the value of the returned <xref:System.Windows.Forms.DialogResult> enumeration if you need to determine which button the user clicked.</span></span>  
  
#### <a name="to-display-the-exception-message-box-with-customized-buttons"></a><span data-ttu-id="e30d4-135">Para exibir a caixa de mensagem de exceção com botões personalizados</span><span class="sxs-lookup"><span data-stu-id="e30d4-135">To display the exception message box with customized buttons</span></span>  
  
1.  <span data-ttu-id="e30d4-136">Adicione uma referência em seu projeto de código gerenciado ao assembly Microsoft.ExceptionMessageBox.dll.</span><span class="sxs-lookup"><span data-stu-id="e30d4-136">Add a reference in your managed code project to the Microsoft.ExceptionMessageBox.dll assembly.</span></span>  
  
2.  <span data-ttu-id="e30d4-137">Adicional Adicione uma `using` diretiva (C#) ou `Imports` (Visual Basic .net) para usar o <xref:Microsoft.SqlServer.MessageBox> namespace.</span><span class="sxs-lookup"><span data-stu-id="e30d4-137">(Optional) Add a `using` (C#) or `Imports` (Visual Basic .NET) directive to use the <xref:Microsoft.SqlServer.MessageBox> namespace.</span></span>  
  
3.  <span data-ttu-id="e30d4-138">Crie uma instância da classe <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox> de uma destas duas maneiras:</span><span class="sxs-lookup"><span data-stu-id="e30d4-138">Create an instance of the <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox> class in one of two ways:</span></span>  
  
    -   <span data-ttu-id="e30d4-139">Passe o <xref:System.Exception> objeto manipulado por um `try` - `catch` bloco.</span><span class="sxs-lookup"><span data-stu-id="e30d4-139">Pass the <xref:System.Exception> object handled by a `try`-`catch` block.</span></span>  
  
    -   <span data-ttu-id="e30d4-140">Passe o texto da mensagem como um valor <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="e30d4-140">Pass the message text as a <xref:System.String> value.</span></span>  
  
4.  <span data-ttu-id="e30d4-141">Defina um dos valores a seguir para <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Buttons%2A>:</span><span class="sxs-lookup"><span data-stu-id="e30d4-141">Set one of the following values for <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Buttons%2A>:</span></span>  
  
    -   <span data-ttu-id="e30d4-142"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.AbortRetryIgnore>-exibe os botões **abortar**, **repetir**e **ignorar** .</span><span class="sxs-lookup"><span data-stu-id="e30d4-142"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.AbortRetryIgnore> - displays the **Abort**, **Retry**, and **Ignore** buttons.</span></span>  
  
    -   <span data-ttu-id="e30d4-143"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.Custom>- exibe botões personalizados.</span><span class="sxs-lookup"><span data-stu-id="e30d4-143"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.Custom> - displays custom buttons.</span></span>  
  
    -   <span data-ttu-id="e30d4-144"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.OK>-exibe o botão **OK** .</span><span class="sxs-lookup"><span data-stu-id="e30d4-144"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.OK> - displays the **OK** button.</span></span>  
  
    -   <span data-ttu-id="e30d4-145"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.OKCancel>-exibe os botões **OK** e **Cancelar** .</span><span class="sxs-lookup"><span data-stu-id="e30d4-145"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.OKCancel> - displays the **OK** and **Cancel** buttons.</span></span>  
  
    -   <span data-ttu-id="e30d4-146"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.RetryCancel>-exibe os botões **repetir** e **Cancelar** .</span><span class="sxs-lookup"><span data-stu-id="e30d4-146"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.RetryCancel> - displays the **Retry** and **Cancel** buttons.</span></span>  
  
    -   <span data-ttu-id="e30d4-147"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.YesNo>-exibe os botões **Sim** e **não** .</span><span class="sxs-lookup"><span data-stu-id="e30d4-147"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.YesNo> - displays **Yes** and **No** buttons.</span></span>  
  
    -   <span data-ttu-id="e30d4-148"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.YesNoCancel>-exibe os botões **Sim**, **não**e **Cancelar** .</span><span class="sxs-lookup"><span data-stu-id="e30d4-148"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.YesNoCancel> - displays **Yes**, **No**, and **Cancel** buttons.</span></span>  
  
5.  <span data-ttu-id="e30d4-149">(Opcional) Se você usar botões personalizados, chame uma das sobrecargas do método <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.SetButtonText%2A> para especificar o texto para até cinco botões personalizados.</span><span class="sxs-lookup"><span data-stu-id="e30d4-149">(Optional) If you use custom buttons, call one of the overloads of the <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.SetButtonText%2A> method to specify text for up to five custom buttons.</span></span>  
  
6.  <span data-ttu-id="e30d4-150">Chame o método <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Show%2A> .</span><span class="sxs-lookup"><span data-stu-id="e30d4-150">Call the <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Show%2A> method.</span></span> <span data-ttu-id="e30d4-151">Passe a janela pai à qual pertence a caixa de mensagem de exceção.</span><span class="sxs-lookup"><span data-stu-id="e30d4-151">Pass the parent window to which the exception message box belongs.</span></span>  
  
7.  <span data-ttu-id="e30d4-152">(Opcional) Observe o valor da enumeração <xref:System.Windows.Forms.DialogResult> retornada se precisar determinar em qual botão o usuário clicou.</span><span class="sxs-lookup"><span data-stu-id="e30d4-152">(Optional) Note the value of the returned <xref:System.Windows.Forms.DialogResult> enumeration if you need to determine which button the user clicked.</span></span> <span data-ttu-id="e30d4-153">Se você usar botões personalizados, observe o valor de <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxDialogResult> para a propriedade <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.CustomDialogResult%2A> para determinar em qual dos botões personalizados o usuário clicou.</span><span class="sxs-lookup"><span data-stu-id="e30d4-153">If you use custom buttons, note the value of <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxDialogResult> for the <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.CustomDialogResult%2A> property to determine which of the custom buttons the user clicked.</span></span>  
  
#### <a name="to-allow-users-to-decide-whether-to-show-the-exception-message-box"></a><span data-ttu-id="e30d4-154">Para permitir que os usuários decidam se mostrarão a caixa de mensagem de exceção</span><span class="sxs-lookup"><span data-stu-id="e30d4-154">To allow users to decide whether to show the exception message box</span></span>  
  
1.  <span data-ttu-id="e30d4-155">Adicione uma referência em seu projeto de código gerenciado ao assembly Microsoft.ExceptionMessageBox.dll.</span><span class="sxs-lookup"><span data-stu-id="e30d4-155">Add a reference in your managed code project to the Microsoft.ExceptionMessageBox.dll assembly.</span></span>  
  
2.  <span data-ttu-id="e30d4-156">Adicional Adicione uma `using` diretiva (C#) ou `Imports` (Visual Basic .net) para usar o <xref:Microsoft.SqlServer.MessageBox> namespace.</span><span class="sxs-lookup"><span data-stu-id="e30d4-156">(Optional) Add a `using` (C#) or `Imports` (Visual Basic .NET) directive to use the <xref:Microsoft.SqlServer.MessageBox> namespace.</span></span>  
  
3.  <span data-ttu-id="e30d4-157">Crie uma instância da classe <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox> de uma destas duas maneiras:</span><span class="sxs-lookup"><span data-stu-id="e30d4-157">Create an instance of the <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox> class in one of two ways:</span></span>  
  
    -   <span data-ttu-id="e30d4-158">Passe o <xref:System.Exception> objeto manipulado por um `try` - `catch` bloco.</span><span class="sxs-lookup"><span data-stu-id="e30d4-158">Pass the <xref:System.Exception> object handled by a `try`-`catch` block.</span></span>  
  
    -   <span data-ttu-id="e30d4-159">Passe o texto da mensagem como um valor <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="e30d4-159">Pass the message text as a <xref:System.String> value.</span></span>  
  
4.  <span data-ttu-id="e30d4-160">Defina a propriedade <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.ShowCheckbox%2A> como `true`.</span><span class="sxs-lookup"><span data-stu-id="e30d4-160">Set the <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.ShowCheckbox%2A> property to `true`.</span></span>  
  
5.  <span data-ttu-id="e30d4-161">(Opcional) Especifique o texto que pede ao usuário decidir se mostrará a caixa de mensagem de exceção novamente para <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.CheckboxText%2A>.</span><span class="sxs-lookup"><span data-stu-id="e30d4-161">(Optional) Specify the text that asks the user to decide whether to show the exception message box again for <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.CheckboxText%2A>.</span></span> <span data-ttu-id="e30d4-162">O texto padrão é "Não exibir esta mensagem novamente".</span><span class="sxs-lookup"><span data-stu-id="e30d4-162">The default text is "Do not show this message again."</span></span>  
  
6.  <span data-ttu-id="e30d4-163">Se precisar manter a decisão do usuário somente durante a execução do aplicativo, defina o valor de <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.IsCheckboxChecked%2A> como uma variável <xref:System.Boolean> global.</span><span class="sxs-lookup"><span data-stu-id="e30d4-163">If you need to keep the user's decision only for the duration of the application's execution, set the value of <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.IsCheckboxChecked%2A> to a global <xref:System.Boolean> variable.</span></span> <span data-ttu-id="e30d4-164">Avalie esse valor antes de criar uma instância da caixa de mensagem de exceção.</span><span class="sxs-lookup"><span data-stu-id="e30d4-164">Evaluate this value before creating an instance of the exception message box.</span></span>  
  
7.  <span data-ttu-id="e30d4-165">Se você precisar armazenar a decisão de um usuário permanentemente, siga este procedimento:</span><span class="sxs-lookup"><span data-stu-id="e30d4-165">If you need to store a user's decision permanently, do the following:</span></span>  
  
    1.  <span data-ttu-id="e30d4-166">Chame o método CreateSubKey para abrir uma chave do Registro personalizada usada pelo seu aplicativo e defina <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.CheckboxRegistryKey%2A> como o objeto RegistryKey retornado.</span><span class="sxs-lookup"><span data-stu-id="e30d4-166">Call the CreateSubKey method to open a custom registry key that your application uses, and set <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.CheckboxRegistryKey%2A> to the returned RegistryKey object.</span></span>  
  
    2.  <span data-ttu-id="e30d4-167">Defina <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.CheckboxRegistryValue%2A> como o nome do valor do Registro que é usado.</span><span class="sxs-lookup"><span data-stu-id="e30d4-167">Set <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.CheckboxRegistryValue%2A> to the name of the registry value that is used.</span></span>  
  
    3.  <span data-ttu-id="e30d4-168">Defina <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.CheckboxRegistryMeansDoNotShowDialog%2A> como `true`.</span><span class="sxs-lookup"><span data-stu-id="e30d4-168">Set <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.CheckboxRegistryMeansDoNotShowDialog%2A> to `true`.</span></span>  
  
    4.  <span data-ttu-id="e30d4-169">Chame o método <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Show%2A> .</span><span class="sxs-lookup"><span data-stu-id="e30d4-169">Call the <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Show%2A> method.</span></span> <span data-ttu-id="e30d4-170">A chave do Registro especificada é avaliada, e a caixa de mensagem de exceção só será exibida se os dados armazenados na chave do Registro forem 0.</span><span class="sxs-lookup"><span data-stu-id="e30d4-170">The specified registry key is evaluated, and the exception message box is displayed only if the data stored in the registry key is 0.</span></span> <span data-ttu-id="e30d4-171">Se a caixa de diálogo for exibida e o usuário marcar a caixa de seleção antes de clicar em um botão, os dados da chave do Registro serão definidos como 1.</span><span class="sxs-lookup"><span data-stu-id="e30d4-171">If the dialog box is displayed and the user selects the check box before clicking a button, the data in the registry key is set to 1.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e30d4-172">Exemplo</span><span class="sxs-lookup"><span data-stu-id="e30d4-172">Example</span></span>  
 <span data-ttu-id="e30d4-173">Este exemplo usa a caixa de mensagem de exceção apenas com o botão **OK** para exibir as informações de uma exceção de aplicativo que inclui a exceção tratada juntamente com outras informações específicas de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="e30d4-173">This example uses the exception message box with only the **OK** button to display information from an application exception that includes the handled exception along with additional application-specific information.</span></span>  
  
 [!code-csharp[HowTo#emb_showOKbutton](../../snippets/csharp/SQL15/replication/howto/cs/embform.cs#emb_showokbutton)]  
  
 [!code-vb[HowTo#emb_vb_showOKbutton](../../snippets/visualbasic/SQL15/replication/howto/vb/embform.vb#emb_vb_showokbutton)]  
  
## <a name="example"></a><span data-ttu-id="e30d4-174">Exemplo</span><span class="sxs-lookup"><span data-stu-id="e30d4-174">Example</span></span>  
 <span data-ttu-id="e30d4-175">Este exemplo usa a caixa de mensagem de exceção com os botões **Sim** e **Não** que o usuário pode escolher.</span><span class="sxs-lookup"><span data-stu-id="e30d4-175">This example uses the exception message box with **Yes** and **No** buttons from which the user chooses.</span></span>  
  
 [!code-csharp[HowTo#emb_showYesNobutton](../../snippets/csharp/SQL15/replication/howto/cs/embform.cs#emb_showyesnobutton)]  
  
 [!code-vb[HowTo#emb_vb_showYesNobutton](../../snippets/visualbasic/SQL15/replication/howto/vb/embform.vb#emb_vb_showyesnobutton)]  
  
## <a name="example"></a><span data-ttu-id="e30d4-176">Exemplo</span><span class="sxs-lookup"><span data-stu-id="e30d4-176">Example</span></span>  
 <span data-ttu-id="e30d4-177">Este exemplo usa a caixa de mensagem de exceção com botões personalizados.</span><span class="sxs-lookup"><span data-stu-id="e30d4-177">This example uses the exception message box with custom buttons.</span></span>  
  
 [!code-csharp[HowTo#emb_showcustombutton](../../snippets/csharp/SQL15/replication/howto/cs/embform.cs#emb_showcustombutton)]  
  
 [!code-vb[HowTo#emb_vb_showcustombutton](../../snippets/visualbasic/SQL15/replication/howto/vb/embform.vb#emb_vb_showcustombutton)]  
  
## <a name="example"></a><span data-ttu-id="e30d4-178">Exemplo</span><span class="sxs-lookup"><span data-stu-id="e30d4-178">Example</span></span>  
 <span data-ttu-id="e30d4-179">Este exemplo usa a caixa de seleção para determinar se a caixa de mensagem de exceção será exibida.</span><span class="sxs-lookup"><span data-stu-id="e30d4-179">This example uses the check box to determine whether to show the exception message box.</span></span>  
  
 [!code-csharp[HowTo#emb_usecheckbox](../../snippets/csharp/SQL15/replication/howto/cs/embform.cs#emb_usecheckbox)]  
  
 [!code-vb[HowTo#emb_vb_usecheckbox](../../snippets/visualbasic/SQL15/replication/howto/vb/embform.vb#emb_vb_usecheckbox)]  
  
## <a name="example"></a><span data-ttu-id="e30d4-180">Exemplo</span><span class="sxs-lookup"><span data-stu-id="e30d4-180">Example</span></span>  
 <span data-ttu-id="e30d4-181">Este exemplo usa a caixa de seleção e uma chave do Registro para determinar se a caixa de mensagem de exceção será exibida.</span><span class="sxs-lookup"><span data-stu-id="e30d4-181">This example uses the check box and a registry key to determine whether to show the exception message box.</span></span>  
  
 [!code-csharp[HowTo#emb_useregkey](../../snippets/csharp/SQL15/replication/howto/cs/embform.cs#emb_useregkey)]  
  
 [!code-vb[HowTo#emb_vb_useregkey](../../snippets/visualbasic/SQL15/replication/howto/vb/embform.vb#emb_vb_useregkey)]  
  
## <a name="example"></a><span data-ttu-id="e30d4-182">Exemplo</span><span class="sxs-lookup"><span data-stu-id="e30d4-182">Example</span></span>  
 <span data-ttu-id="e30d4-183">Este exemplo usa a caixa de mensagem de exceção para mostrar informações adicionais úteis ao solucionar problemas ou depurar.</span><span class="sxs-lookup"><span data-stu-id="e30d4-183">This example uses the exception message box to show additional information that is helpful when troubleshooting or debugging.</span></span>  
  
 [!code-csharp[HowTo#emb_moreinfo](../../snippets/csharp/SQL15/replication/howto/cs/embform.cs#emb_moreinfo)]  
  
 [!code-vb[HowTo#emb_vb_moreinfo](../../snippets/visualbasic/SQL15/replication/howto/vb/embform.vb#emb_vb_moreinfo)]  
  
  
