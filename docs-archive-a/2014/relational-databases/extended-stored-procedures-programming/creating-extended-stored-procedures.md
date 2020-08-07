---
title: Criando procedimentos armazenados estendidos | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- warnings [SQL Server]
- extended stored procedures [SQL Server], debugging
- extended stored procedures [SQL Server], creating
- messages [SQL Server], extended stored procedures
ms.assetid: 9f7c0cdb-6d88-44c0-b049-29953ae75717
author: rothja
ms.author: jroth
ms.openlocfilehash: d243b27b8542ec5fe10d795de1729d6c1fe484c3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576399"
---
# <a name="creating-extended-stored-procedures"></a><span data-ttu-id="8ce10-102">Criando procedimentos armazenados estendidos</span><span class="sxs-lookup"><span data-stu-id="8ce10-102">Creating Extended Stored Procedures</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="8ce10-103">Em vez disso, use a integração CLR.</span><span class="sxs-lookup"><span data-stu-id="8ce10-103">Use CLR Integration instead.</span></span>  
  
 <span data-ttu-id="8ce10-104">Um procedimento armazenado estendido é uma função com um protótipo:</span><span class="sxs-lookup"><span data-stu-id="8ce10-104">An extended stored procedure is a function with a prototype:</span></span>  
  
 <span data-ttu-id="8ce10-105">SRVRETCODE *xp_extendedProcName* **(** SRVPROC **\*);**</span><span class="sxs-lookup"><span data-stu-id="8ce10-105">SRVRETCODE *xp_extendedProcName* **(** SRVPROC **\*);**</span></span>  
  
 <span data-ttu-id="8ce10-106">O uso do prefixo xp_ é opcional.</span><span class="sxs-lookup"><span data-stu-id="8ce10-106">Using the prefix xp_ is optional.</span></span> <span data-ttu-id="8ce10-107">Os nomes de procedimento armazenado estendido fazem distinção de maiúsculas e minúsculas quando mencionados em instruções [!INCLUDE[tsql](../../includes/tsql-md.md)], independentemente da página de código/ordem de classificação instalada no servidor.</span><span class="sxs-lookup"><span data-stu-id="8ce10-107">Extended stored procedure names are case sensitive when referenced in [!INCLUDE[tsql](../../includes/tsql-md.md)] statements, regardless of code page/sort order installed on the server.</span></span> <span data-ttu-id="8ce10-108">Quando você compila uma DLL:</span><span class="sxs-lookup"><span data-stu-id="8ce10-108">When you build a DLL:</span></span>  
  
-   <span data-ttu-id="8ce10-109">Se um ponto de entrada for necessário, grave uma função DllMain.</span><span class="sxs-lookup"><span data-stu-id="8ce10-109">If an entry point is necessary, write a DllMain function.</span></span>  
  
     <span data-ttu-id="8ce10-110">Essa função será opcional; se você não a fornecer em código-fonte, o compilador vinculará sua própria versão, o que não resultará em nada, mas retornará TRUE.</span><span class="sxs-lookup"><span data-stu-id="8ce10-110">This function is optional; if you do not provide it in source code, the compiler links its own version, which does nothing but return TRUE.</span></span> <span data-ttu-id="8ce10-111">Se você fornecer uma função DllMain, o sistema operacional chamará essa função quando um thread ou processo for anexado ou desanexado da DLL.</span><span class="sxs-lookup"><span data-stu-id="8ce10-111">If you provide a DllMain function, the operating system calls this function when a thread or process attaches to or detaches from the DLL.</span></span>  
  
-   <span data-ttu-id="8ce10-112">Todas as funções chamadas de fora da DLL (todas as Efunctions do procedimento armazenado estendido) devem ser exportadas.</span><span class="sxs-lookup"><span data-stu-id="8ce10-112">All functions called from outside the DLL (all extended stored procedure Efunctions) must be exported.</span></span>  
  
     <span data-ttu-id="8ce10-113">Você pode exportar uma função listando seu nome na seção Exports de um arquivo. def ou pode prefixar o nome da função no código-fonte com __declspec (dllexport), uma extensão do compilador da Microsoft (Observe que \_ _declspec () começa com dois sublinhados).</span><span class="sxs-lookup"><span data-stu-id="8ce10-113">You can export a function by listing its name in the EXPORTS section of a .def file, or you can prefix the function name in the source code with __declspec(dllexport), a Microsoft compiler extension (Note that \__declspec() begins with two underscores).</span></span>  
  
 <span data-ttu-id="8ce10-114">Estes arquivos são necessários para criar uma DLL de procedimento armazenado estendido.</span><span class="sxs-lookup"><span data-stu-id="8ce10-114">These files are required for creating an extended stored procedure DLL.</span></span>  
  
|<span data-ttu-id="8ce10-115">Arquivo</span><span class="sxs-lookup"><span data-stu-id="8ce10-115">File</span></span>|<span data-ttu-id="8ce10-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="8ce10-116">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="8ce10-117">Srv.h</span><span class="sxs-lookup"><span data-stu-id="8ce10-117">Srv.h</span></span>|<span data-ttu-id="8ce10-118">Arquivo de cabeçalho da API do Procedimento Armazenado Estendido</span><span class="sxs-lookup"><span data-stu-id="8ce10-118">Extended Stored Procedure API header file</span></span>|  
|<span data-ttu-id="8ce10-119">Opends60.lib</span><span class="sxs-lookup"><span data-stu-id="8ce10-119">Opends60.lib</span></span>|<span data-ttu-id="8ce10-120">Biblioteca de importação para Opends60.dll</span><span class="sxs-lookup"><span data-stu-id="8ce10-120">Import library for Opends60.dll</span></span>|  
  
 <span data-ttu-id="8ce10-121">Para criar uma DLL de procedimento armazenado estendido, crie um projeto do tipo Biblioteca de Vínculo Dinâmico.</span><span class="sxs-lookup"><span data-stu-id="8ce10-121">To create an extended stored procedure DLL, create a project of type Dynamic Link Library.</span></span> <span data-ttu-id="8ce10-122">Para obter mais informações sobre a criação de uma DLL, consulte a documentação do ambiente de desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="8ce10-122">For more information about creating a DLL, see the development environment documentation.</span></span>  
  
 <span data-ttu-id="8ce10-123">É altamente recomendado que todas as DLLs de procedimento armazenado estendido implementem e exportem a seguinte função:</span><span class="sxs-lookup"><span data-stu-id="8ce10-123">It is highly recommended that all extended stored procedure DLLs implement and export the following function:</span></span>  
  
```  
__declspec(dllexport) ULONG __GetXpVersion()  
{  
   return ODS_VERSION;  
}  
```  
  
> [!NOTE]  
>  <span data-ttu-id="8ce10-124">__declspec(dllexport) é uma extensão de compilador específica da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8ce10-124">__declspec(dllexport) is a Microsoft-specific compiler extension.</span></span> <span data-ttu-id="8ce10-125">Se seu compilador não aceitar esta diretiva, você deverá exportar esta função no arquivo DEF, na seção EXPORTS.</span><span class="sxs-lookup"><span data-stu-id="8ce10-125">If your compiler does not support this directive, you should export this function in your DEF file under the EXPORTS section.</span></span>  
  
 <span data-ttu-id="8ce10-126">Quando o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] for iniciado com o sinalizador de rastreamento-T260 ou se um usuário com privilégios de administrador do sistema executar o rastreamento DBCC (260) e se a DLL de procedimento armazenado estendido não oferecer suporte a __GetXpVersion (), uma mensagem de aviso (erro 8131: dll de procedimento armazenado estendido '% ' não exporta \_ _GetXpVersion ().) é impressa no log de erros.</span><span class="sxs-lookup"><span data-stu-id="8ce10-126">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is started with the trace flag -T260 or if a user with system administrator privileges runs DBCC TRACEON (260), and if the extended stored procedure DLL does not support __GetXpVersion(), a warning message (Error 8131: Extended stored procedure DLL '%' does not export \__GetXpVersion().) is printed to the error log.</span></span> <span data-ttu-id="8ce10-127">(Observe que \_ _GetXpVersion () começa com dois sublinhados.)</span><span class="sxs-lookup"><span data-stu-id="8ce10-127">(Note that \__GetXpVersion() begins with two underscores.)</span></span>  
  
 <span data-ttu-id="8ce10-128">Se a DLL de procedimento armazenado estendido exportar __GetXpVersion(), mas a versão retornada pela função for menor que aquela exigida pelo servidor, uma mensagem de aviso informando a versão retornada pela função e a versão esperada pelo servidor será impressa no log de erros.</span><span class="sxs-lookup"><span data-stu-id="8ce10-128">If the extended stored procedure DLL exports __GetXpVersion(), but the version returned by the function is less than that required by the server, a warning message stating the version returned by the function and the version expected by the server is printed to the error log.</span></span> <span data-ttu-id="8ce10-129">Se você receber essa mensagem, você está retornando um valor incorreto de \_ _GetXpVersion () ou está compilando com uma versão mais antiga do SRV. h.</span><span class="sxs-lookup"><span data-stu-id="8ce10-129">If you get this message, you are returning an incorrect value from \__GetXpVersion(), or you are compiling with an older version of srv.h.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8ce10-130">SetErrorMode, uma função do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Win32, não deve ser chamada em procedimentos armazenados estendidos.</span><span class="sxs-lookup"><span data-stu-id="8ce10-130">SetErrorMode, a [!INCLUDE[msCoName](../../includes/msconame-md.md)] Win32 function, should not be called in extended stored procedures.</span></span>  
  
 <span data-ttu-id="8ce10-131">Será recomendável que um procedimento armazenado estendido de execução demorada chame srv_got_attention periodicamente, de forma que o procedimento possa ser encerrado por si mesmo se a conexão for interrompida ou o lote for anulado.</span><span class="sxs-lookup"><span data-stu-id="8ce10-131">It is recommended that a long-running extended stored procedure should call srv_got_attention periodically so that the procedure can terminate itself if the connection is killed or the batch is aborted.</span></span>  
  
 <span data-ttu-id="8ce10-132">Para depurar uma DLL de procedimento armazenado estendido, copie-a no diretório [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\Binn.</span><span class="sxs-lookup"><span data-stu-id="8ce10-132">To debug an extended stored procedure DLL, copy it to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\Binn directory.</span></span> <span data-ttu-id="8ce10-133">Para especificar o executável para a sessão de depuração, insira o caminho e o nome do arquivo [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] executável (por exemplo, C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Binn\Sqlservr.exe).</span><span class="sxs-lookup"><span data-stu-id="8ce10-133">To specify the executable for the debugging session, enter the path and file name of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] executable file (for example, C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Binn\Sqlservr.exe).</span></span> <span data-ttu-id="8ce10-134">Para obter informações sobre argumentos sqlservr, consulte [aplicativo sqlservr](../../tools/sqlservr-application.md).</span><span class="sxs-lookup"><span data-stu-id="8ce10-134">For information about sqlservr arguments, see [sqlservr Application](../../tools/sqlservr-application.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ce10-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8ce10-135">See Also</span></span>  
 [<span data-ttu-id="8ce10-136">srv_got_attention &#40;API de procedimento armazenado estendido&#41;</span><span class="sxs-lookup"><span data-stu-id="8ce10-136">srv_got_attention &#40;Extended Stored Procedure API&#41;</span></span>](../extended-stored-procedures-reference/srv-got-attention-extended-stored-procedure-api.md)  
  
  
