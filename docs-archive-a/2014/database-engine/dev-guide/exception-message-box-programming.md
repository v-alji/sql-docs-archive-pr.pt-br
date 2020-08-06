---
title: Programação da caixa de mensagem de exceção | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
helpviewer_keywords:
- ExceptionMessageBox class, about ExceptionMessageBox class
- exception message box [SQL Server], about exception message box
- exception message box [SQL Server]
- interfaces [SQL Server]
- exceptions [SQL Server]
- messages [SQL Server], exception message box
ms.assetid: 0b1ba514-6959-4e69-bfd2-3cf3c1ac4b9c
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: b2425169f838199ce24b4331dd57c74b480adf62
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685914"
---
# <a name="exception-message-box-programming"></a><span data-ttu-id="45a03-102">Programação da caixa de mensagem de exceção</span><span class="sxs-lookup"><span data-stu-id="45a03-102">Exception Message Box Programming</span></span>
  <span data-ttu-id="45a03-103">A caixa de mensagem de exceção é uma interface programática que é instalada com o e usada por [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] componentes gráficos.</span><span class="sxs-lookup"><span data-stu-id="45a03-103">The exception message box is a programmatic interface that is installed with and used by [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] graphical components.</span></span> <span data-ttu-id="45a03-104">A caixa de mensagem de exceção é um assembly gerenciado com suporte que você pode usar em aplicativos para proporcionar um controle significativamente maior sobre a experiência de troca de mensagens e oferecer aos usuários as opções de salvar o conteúdo da mensagem de erro para referência futura e obter ajuda sobre mensagens.</span><span class="sxs-lookup"><span data-stu-id="45a03-104">The exception message box is a supported managed assembly that you can use in your applications to provide significantly more control over the messaging experience and to give your users the options to save error message content for later reference and to get help on messages.</span></span> <span data-ttu-id="45a03-105">Como a caixa de mensagem de exceção é instalada por todas as edições do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssEW](../../includes/ssew-md.md)] , exceto, você pode usá-la sem nenhuma configuração adicional em qualquer computador em que os [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] componentes cliente tenham sido instalados.</span><span class="sxs-lookup"><span data-stu-id="45a03-105">Because the exception message box is installed by all editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] except [!INCLUDE[ssEW](../../includes/ssew-md.md)], you can use it with no additional configuration on any computer on which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client components have been installed.</span></span>  
  
 <span data-ttu-id="45a03-106">A classe <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox> no namespace <xref:Microsoft.SqlServer.MessageBox> tem todas as funcionalidades da classe <xref:System.Windows.Forms.MessageBox> e muito mais.</span><span class="sxs-lookup"><span data-stu-id="45a03-106">The <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox> class in the <xref:Microsoft.SqlServer.MessageBox> namespace has all the functionality of the <xref:System.Windows.Forms.MessageBox> class and more.</span></span> <span data-ttu-id="45a03-107">Ideal para qualquer tarefa na qual <xref:System.Windows.Forms.MessageBox> possa ser usado, a <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox> foi projetada para tratar exceções de código gerenciado de forma esmerada.</span><span class="sxs-lookup"><span data-stu-id="45a03-107">Ideal for any tasks for which <xref:System.Windows.Forms.MessageBox> may be used, <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox> is designed to elegantly handle managed code exceptions.</span></span> <span data-ttu-id="45a03-108">A caixa de mensagem de exceção permite que você faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="45a03-108">The exception message box allows you to do the following:</span></span>  
  
-   <span data-ttu-id="45a03-109">Forneça texto de botão personalizado para até cinco botões.</span><span class="sxs-lookup"><span data-stu-id="45a03-109">Provide customized button text for up to five buttons.</span></span> <span data-ttu-id="45a03-110">Os botões e a caixa de diálogo são redimensionados automaticamente para diferentes comprimentos de texto.</span><span class="sxs-lookup"><span data-stu-id="45a03-110">Buttons and the dialog box resize automatically for different text lengths.</span></span>  
  
-   <span data-ttu-id="45a03-111">Permita que os usuários copiem o título da mensagem, o texto, o texto do botão e os links de ajuda (se houver) com facilidade para a Área de Transferência ou envie essas informações em uma mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="45a03-111">Allow users to easily copy the message title, text, button text, and help links (if any) to the Clipboard or send this information in an e-mail message.</span></span>  
  
-   <span data-ttu-id="45a03-112">Exibe todas as exceções e erros subjacentes em uma árvore de relações hierárquica quando os usuários clicam em **informações adicionais**.</span><span class="sxs-lookup"><span data-stu-id="45a03-112">Display all underlying exceptions and errors in a hierarchical relationship tree when users click **Additional Information**.</span></span>  
  
-   <span data-ttu-id="45a03-113">Permita que os usuários decidam se a mensagem deverá ser exibida quando a mesma exceção ocorrer novamente.</span><span class="sxs-lookup"><span data-stu-id="45a03-113">Allow users to decide whether to display the message when the same exception occurs again.</span></span>  
  
-   <span data-ttu-id="45a03-114">Acesse um sistema de ajuda online usando um link de ajuda associado à exceção.</span><span class="sxs-lookup"><span data-stu-id="45a03-114">Access an online help system by using a help link associated with the exception.</span></span>  
  
 <span data-ttu-id="45a03-115">Para obter mais informações, consulte [caixa de mensagem de exceção do programa](../../../2014/database-engine/dev-guide/program-exception-message-box.md).</span><span class="sxs-lookup"><span data-stu-id="45a03-115">For more information, see [Program Exception Message Box](../../../2014/database-engine/dev-guide/program-exception-message-box.md).</span></span>  
  
  
