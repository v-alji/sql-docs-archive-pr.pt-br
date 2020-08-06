---
title: Definir um tamanho máximo de arquivo para um arquivo de rastreamento (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- maximum file size for traces
- size [SQL Server], trace files
ms.assetid: e86dc4ce-5aa3-4c0d-acb5-c9e8871ed963
author: stevestein
ms.author: sstein
ms.openlocfilehash: aa990c610f7aa8bf82690c8c201c6643eb712191
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683242"
---
# <a name="set-a-maximum-file-size-for-a-trace-file-sql-server-profiler"></a><span data-ttu-id="a70e5-102">Definir um tamanho máximo para um arquivo de rastreamento (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="a70e5-102">Set a Maximum File Size for a Trace File (SQL Server Profiler)</span></span>
  <span data-ttu-id="a70e5-103">Use o procedimento a seguir para definir um tamanho máximo para um arquivo de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="a70e5-103">Use the following procedure to set the maximum file size for a trace file.</span></span>  
  
### <a name="to-set-a-maximum-file-size-for-a-trace-file"></a><span data-ttu-id="a70e5-104">Para definir um tamanho máximo para um arquivo de rastreamento</span><span class="sxs-lookup"><span data-stu-id="a70e5-104">To set a maximum file size for a trace file</span></span>  
  
1.  <span data-ttu-id="a70e5-105">No menu **Arquivo** , clique em **Novo Rastreamento**e conecte-se a uma instância do Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a70e5-105">On the **File** menu, click **New Trace**, and then connect to an instance of Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="a70e5-106">A caixa de diálogo **Propriedades do Rastreamento**é exibida.</span><span class="sxs-lookup"><span data-stu-id="a70e5-106">The **Trace Properties**dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a70e5-107">Se **Iniciar rastreamento imediatamente após estabelecer a conexão**estiver selecionado, a caixa de diálogo **Propriedades do Rastreamento**não será exibida e o rastreamento será iniciado.</span><span class="sxs-lookup"><span data-stu-id="a70e5-107">If **Start tracing immediately after making connection**is selected, the **Trace Properties**dialog box fails to appear and the trace begins instead.</span></span> <span data-ttu-id="a70e5-108">Para desabilitar essa configuração, no menu **Ferramentas**, clique em **Opções**e desmarque a caixa de seleção **Iniciar rastreamento imediatamente após estabelecer a conexão** .</span><span class="sxs-lookup"><span data-stu-id="a70e5-108">To turn off this setting, on the **Tools**menu, click **Options**, and clear the **Start tracing immediately after making connection** check box.</span></span>  
  
2.  <span data-ttu-id="a70e5-109">Na caixa **Nome do rastreamento** , digite um nome para o rastreamento.</span><span class="sxs-lookup"><span data-stu-id="a70e5-109">In the **Trace name** box, type a name for the trace.</span></span>  
  
3.  <span data-ttu-id="a70e5-110">Na lista **Nome do modelo**, selecione um modelo de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="a70e5-110">In the **Template name**list, select a trace template.</span></span>  
  
4.  <span data-ttu-id="a70e5-111">Selecione **Salvar em arquivo**e especifique um arquivo em que serão armazenadas as informações do rastreamento.</span><span class="sxs-lookup"><span data-stu-id="a70e5-111">Select **Save to file**, and then specify a file to store the trace information.</span></span>  
  
5.  <span data-ttu-id="a70e5-112">Na caixa de seleção **Definir tamanho máximo do arquivo** , especifique um tamanho do arquivo máximo para o rastreamento.</span><span class="sxs-lookup"><span data-stu-id="a70e5-112">In the **Set maximum file size** check box, specify a maximum file size for the trace.</span></span> <span data-ttu-id="a70e5-113">Quando o tamanho de arquivo alcançar esse máximo, os eventos do rastreamento deixarão de ser registrados no arquivo.</span><span class="sxs-lookup"><span data-stu-id="a70e5-113">When the file size reaches this maximum, trace events are no longer recorded in this file.</span></span> <span data-ttu-id="a70e5-114">Se você selecionar **Habilitar substituição de arquivo** (que está selecionado por padrão), ocorrerá o seguinte:</span><span class="sxs-lookup"><span data-stu-id="a70e5-114">If you select **Enable file rollover** (which is selected by default),the following occurs:</span></span>  
  
     <span data-ttu-id="a70e5-115">A opção de substituição de arquivo faz com que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] feche o arquivo atual e crie um novo arquivo quando o tamanho máximo é atingido.</span><span class="sxs-lookup"><span data-stu-id="a70e5-115">The file rollover option causes [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to close the current file and create a new file when the maximum file size is reached.</span></span> <span data-ttu-id="a70e5-116">O novo arquivo recebe o mesmo nome do arquivo anterior, acrescido de um número inteiro indicando a sua sequência; por exemplo, se o arquivo de rastreamento original for denominado nomedoarquivo_1.trc, o arquivo seguinte será nomeado nomedoarquivo_2.trc, e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="a70e5-116">The new file has the same name as the previous file, but an integer is appended to the name to indicate its sequence; for example, if the original trace file is named filename_1.trc, the next trace file is filename_2.trc, and so on.</span></span> <span data-ttu-id="a70e5-117">Se o nome atribuído a um novo arquivo de substituição já estiver sendo usado por um arquivo existente, este último será substituído, exceto se for somente leitura.</span><span class="sxs-lookup"><span data-stu-id="a70e5-117">If the name assigned to a new rollover file is already used by an existing file, the existing file is overwritten unless it is read-only.</span></span> <span data-ttu-id="a70e5-118">A opção de substituição de arquivo é habilitada por padrão quando você salva dados de rastreamento em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="a70e5-118">The file rollover option is enabled by default when you are saving trace data to a file.</span></span>  
  
     <span data-ttu-id="a70e5-119">Com a opção de substituição de arquivo ativada, o rastreamento continua até que seja interrompido de alguma outra maneira.</span><span class="sxs-lookup"><span data-stu-id="a70e5-119">With the file rollover option on, the trace continues until it is stopped by some other means.</span></span> <span data-ttu-id="a70e5-120">Para interromper o rastreamento quando o limite de tamanho de arquivo for atingido, desabilite a opção de substituição de arquivo.</span><span class="sxs-lookup"><span data-stu-id="a70e5-120">To stop the trace after you have reached the file size limit, disable the file rollover option.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a70e5-121">O sistema de arquivos FAT32 limita arquivos a um pouco menos de 4 gigabytes (GB).</span><span class="sxs-lookup"><span data-stu-id="a70e5-121">The FAT32 file system limits files to slightly less than 4 gigabytes (GB).</span></span> <span data-ttu-id="a70e5-122">Quando o arquivo de rastreamento atinge esse tamanho, o rastreamento falha com o erro "Espaço em disco insuficiente".</span><span class="sxs-lookup"><span data-stu-id="a70e5-122">When the trace file reaches that size, the trace fails with the error "Not enough disk space."</span></span> <span data-ttu-id="a70e5-123">Para criar arquivos maiores, use o sistema de arquivos NTFS.</span><span class="sxs-lookup"><span data-stu-id="a70e5-123">To create larger files, use the NTFS file system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a70e5-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a70e5-124">See Also</span></span>  
 [<span data-ttu-id="a70e5-125">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="a70e5-125">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
