---
title: Editor da tarefa FTP (página Geral) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.ftptask.general.f1
helpviewer_keywords:
- File Transfer Protocol Task Editor
ms.assetid: 28b46fdd-b04a-4f97-a99f-883f5735a6d9
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0cb4ffe2fa44e76890f6b70912f84dbcaa8f2cd0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571445"
---
# <a name="ftp-task-editor-general-page"></a><span data-ttu-id="a47a0-102">Editor da Tarefa FTP (página Geral)</span><span class="sxs-lookup"><span data-stu-id="a47a0-102">FTP Task Editor (General Page)</span></span>
  <span data-ttu-id="a47a0-103">Use a página **Geral** da caixa de diálogo **Editor da Tarefa FTP** para especificar o gerenciador de conexões que estabelece conexão com o servidor FTP com o qual a tarefa se comunica.</span><span class="sxs-lookup"><span data-stu-id="a47a0-103">Use the **General** page of the **FTP Task Editor** dialog box to specify the FTP connection manager that connects to the FTP server that the task communicates with.</span></span> <span data-ttu-id="a47a0-104">Você também pode nomear e descrever a tarefa FTP.</span><span class="sxs-lookup"><span data-stu-id="a47a0-104">You can also name and describe the FTP task.</span></span>  
  
 <span data-ttu-id="a47a0-105">Para obter informações sobre essa tarefa, consulte [Tarefa FTP](control-flow/ftp-task.md).</span><span class="sxs-lookup"><span data-stu-id="a47a0-105">To learn about this task, see [FTP Task](control-flow/ftp-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="a47a0-106">Opções</span><span class="sxs-lookup"><span data-stu-id="a47a0-106">Options</span></span>  
 <span data-ttu-id="a47a0-107">**FtpConnection**</span><span class="sxs-lookup"><span data-stu-id="a47a0-107">**FtpConnection**</span></span>  
 <span data-ttu-id="a47a0-108">Selecione um gerenciador de conexões FTP existente ou clique em \<**New connection...**> para criar um gerenciador de conexões.</span><span class="sxs-lookup"><span data-stu-id="a47a0-108">Select an existing FTP connection manager, or click \<**New connection...**> to create a connection manager.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a47a0-109">O gerenciador de conexões de FTP dá suporte apenas para autenticação anônima e autenticação básica.</span><span class="sxs-lookup"><span data-stu-id="a47a0-109">The FTP connection manager supports only anonymous authentication and basic authentication.</span></span> <span data-ttu-id="a47a0-110">Ele não suporta a Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="a47a0-110">It does not support Windows Authentication.</span></span>  
  
 <span data-ttu-id="a47a0-111">**Tópicos relacionados**: [Gerenciador de Conexões de FTP](connection-manager/ftp-connection-manager.md), [Editor do Gerenciador de Conexões de FTP](../../2014/integration-services/ftp-connection-manager-editor.md)</span><span class="sxs-lookup"><span data-stu-id="a47a0-111">**Related Topics**: [FTP Connection Manager](connection-manager/ftp-connection-manager.md), [FTP Connection Manager Editor](../../2014/integration-services/ftp-connection-manager-editor.md)</span></span>  
  
 <span data-ttu-id="a47a0-112">**StopOnFailure**</span><span class="sxs-lookup"><span data-stu-id="a47a0-112">**StopOnFailure**</span></span>  
 <span data-ttu-id="a47a0-113">Indique se a tarefa FTP deve ser encerrada se a operação FTP falhar.</span><span class="sxs-lookup"><span data-stu-id="a47a0-113">Indicate whether the FTP task terminates if an FTP operation fails.</span></span>  
  
 <span data-ttu-id="a47a0-114">**Nome**</span><span class="sxs-lookup"><span data-stu-id="a47a0-114">**Name**</span></span>  
 <span data-ttu-id="a47a0-115">Forneça um nome exclusivo para a tarefa FTP.</span><span class="sxs-lookup"><span data-stu-id="a47a0-115">Provide a unique name for the FTP task.</span></span> <span data-ttu-id="a47a0-116">Esse nome é usado como rótulo no ícone de tarefa.</span><span class="sxs-lookup"><span data-stu-id="a47a0-116">This name is used as the label in the task icon.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a47a0-117">Os nomes das tarefas devem ser exclusivos em um pacote.</span><span class="sxs-lookup"><span data-stu-id="a47a0-117">Task names must be unique within a package.</span></span>  
  
 <span data-ttu-id="a47a0-118">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="a47a0-118">**Description**</span></span>  
 <span data-ttu-id="a47a0-119">Digite uma descrição para a tarefa FTP.</span><span class="sxs-lookup"><span data-stu-id="a47a0-119">Type a description of the FTP task.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a47a0-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a47a0-120">See Also</span></span>  
 <span data-ttu-id="a47a0-121">[Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="a47a0-121">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="a47a0-122">[Editor da tarefa FTP &#40;página transferência de arquivos&#41;](../../2014/integration-services/ftp-task-editor-file-transfer-page.md) </span><span class="sxs-lookup"><span data-stu-id="a47a0-122">[FTP Task Editor &#40;File Transfer Page&#41;](../../2014/integration-services/ftp-task-editor-file-transfer-page.md) </span></span>  
 [<span data-ttu-id="a47a0-123">Página Expressões</span><span class="sxs-lookup"><span data-stu-id="a47a0-123">Expressions Page</span></span>](expressions/expressions-page.md)  
  
  
