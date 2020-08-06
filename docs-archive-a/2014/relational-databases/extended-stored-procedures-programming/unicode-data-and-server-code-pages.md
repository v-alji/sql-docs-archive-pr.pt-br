---
title: Dados Unicode e páginas de código do servidor | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- metadata [SQL Server], stored procedures
- Unicode [SQL Server], extended stored procedures
- extended stored procedures [SQL Server], metadata
ms.assetid: 52310260-a892-4b27-ad2e-bf164b98ee80
author: rothja
ms.author: jroth
ms.openlocfilehash: e88a43ee242e9fa84ac3a5573c7d3ca3dc0369d5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568573"
---
# <a name="unicode-data-and-server-code-pages"></a><span data-ttu-id="8029a-102">Páginas de código do servidor e dados Unicode</span><span class="sxs-lookup"><span data-stu-id="8029a-102">Unicode Data and Server Code Pages</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="8029a-103">Em vez disso, use a integração CLR.</span><span class="sxs-lookup"><span data-stu-id="8029a-103">Use CLR Integration instead.</span></span>  
  
 <span data-ttu-id="8029a-104">A API de procedimento armazenado estendido é habilitada para dados Unicode; porém, não é habilitada para metadados Unicode.</span><span class="sxs-lookup"><span data-stu-id="8029a-104">The Extended Stored Procedure API is enabled for Unicode data; however, it is not enabled for Unicode metadata.</span></span> <span data-ttu-id="8029a-105">O diretiva Unicode #define não tem nenhum efeito sobre a API de procedimento armazenado estendido.</span><span class="sxs-lookup"><span data-stu-id="8029a-105">The #define Unicode directive does not have any effect on the Extended Stored Procedure API.</span></span>  
  
 <span data-ttu-id="8029a-106">Pressupõe-se que todos os metadados retornados pela API de procedimento armazenado estendido ou fornecidos para ela pelo seu aplicativo de procedimento armazenado estendido estejam na página de código multibyte do servidor.</span><span class="sxs-lookup"><span data-stu-id="8029a-106">All metadata returned by, or provided to the Extended Stored Procedure API by your extended stored procedure application is assumed to be in the multibyte code page of the server.</span></span> <span data-ttu-id="8029a-107">A página de código padrão de um aplicativo de servidor de API de procedimento armazenado estendido é a página de código ANSI do computador no qual o aplicativo está sendo executado, que pode ser obtido chamando **srv_pfield** com o parâmetro de campo definido como SRV_SPROC_CODEPAGE.</span><span class="sxs-lookup"><span data-stu-id="8029a-107">The default code page of an Extended Stored Procedure API server application is the ANSI code page of the computer on which the application is running, which can be obtained by calling **srv_pfield** with the field parameter set to SRV_SPROC_CODEPAGE.</span></span>  
  
 <span data-ttu-id="8029a-108">Se seu aplicativo de API de procedimento armazenado estendido for compatível com Unicode, você deverá converter os nomes das colunas de metadados Unicode, as mensagens de erro e assim por diante em dados multibyte antes de passar esses dados para a API de procedimento armazenado estendido.</span><span class="sxs-lookup"><span data-stu-id="8029a-108">If your Extended Stored Procedure API application is Unicode-enabled, you must convert your Unicode metadata column names, error messages, and so on, to multibyte data before passing this data to the Extended Stored Procedure API.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8029a-109">Exemplo</span><span class="sxs-lookup"><span data-stu-id="8029a-109">Example</span></span>  
 <span data-ttu-id="8029a-110">O procedimento armazenado estendido a seguir fornece um exemplo de conversões de Unicode.</span><span class="sxs-lookup"><span data-stu-id="8029a-110">The following extended stored procedure provides an example of the Unicode conversions discussed.</span></span> <span data-ttu-id="8029a-111">Observe que:</span><span class="sxs-lookup"><span data-stu-id="8029a-111">Note that:</span></span>  
  
-   <span data-ttu-id="8029a-112">Os dados da coluna são passados como dados Unicode para **srv_describe** porque a coluna está descrita como SRVNVARCHAR.</span><span class="sxs-lookup"><span data-stu-id="8029a-112">Column data is passed as Unicode data to **srv_describe** because the column is described to be SRVNVARCHAR.</span></span>  
  
-   <span data-ttu-id="8029a-113">Os metadados de nome de coluna são passados para **srv_describe** como dados multibyte.</span><span class="sxs-lookup"><span data-stu-id="8029a-113">Column name metadata is passed to **srv_describe** as multibyte data.</span></span>  
  
     <span data-ttu-id="8029a-114">O procedimento armazenado estendido chama **srv_pfield** com o parâmetro Field definido como SRV_SPROC_CODEPAGE para obter a página de código multibyte de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8029a-114">The extended stored procedure calls **srv_pfield** with the field parameter set to SRV_SPROC_CODEPAGE to obtain the multibyte code page of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="8029a-115">As mensagens de erro são passadas para **srv_sendmsg** como dados multibyte.</span><span class="sxs-lookup"><span data-stu-id="8029a-115">Error messages are passed to **srv_sendmsg** as multibyte data.</span></span>  
  
    ```  
    __declspec(dllexport) RETCODE proc1 (SRV_PROC *srvproc)  
    {  
        #define MAX_COL_NAME_LEN 25  
        #define MAX_COL_DATA_LEN 50  
        #define MAX_ERR_MSG_LEN 250  
        #define MAX_SERVER_ERROR 20000  
        #define XP_ERROR_NUMBER MAX_SERVER_ERROR+1  
  
        int retval;  
        UINT serverCodePage;  
        CHAR *szServerCodePage;  
  
        WCHAR unicodeColumnName[MAX_COL_NAME_LEN];  
        CHAR multibyteColumnName[MAX_COL_NAME_LEN];  
  
        WCHAR unicodeColumnData[MAX_COL_DATA_LEN];  
  
        WCHAR unicodeErrorMessage[MAX_ERR_MSG_LEN];  
        CHAR  multibyteErrorMessage[MAX_ERR_MSG_LEN];  
  
        lstrcpyW (unicodeColumnName, L"column1");  
        lstrcpyW (unicodeColumnData, L"column1 data");  
        lstrcpyW (unicodeErrorMessage, L"No Error!");  
  
        // Obtain server code page.  
        //  
        szServerCodePage = srv_pfield (srvproc, SRV_SPROC_CODEPAGE, NULL);      
        if (NULL != szServerCodePage)  
            serverCodePage = atol(szServerCodePage);  
        else   
        {   // Problem situation exists.  
            srv_senddone(srvproc, (SRV_DONE_ERROR | SRV_DONE_MORE), 0, 0);  
            return 1;  
        }  
  
        // Convert column name for Unicode to multibyte using the   
        // server code page.  
        //  
        retval = WideCharToMultiByte(    
            serverCodePage,                 // code page  
            0,                              // default  
            unicodeColumnName,              // wide-character string  
            -1,                             // string is null terminated  
            multibyteColumnName,            // address of buffer for new  
                                            //   string  
            sizeof (multibyteColumnName),   // size of buffer  
            NULL, NULL);  
  
        if (0 == retval)  
        {  
            lstrcpyW (unicodeErrorMessage, L"Conversion to multibyte  
            failed.");  
            goto Error;  
        }  
  
        retval = srv_describe (srvproc, 1, multibyteColumnName,  
        SRV_NULLTERM,   
          SRVNVARCHAR, MAX_COL_DATA_LEN*sizeof(WCHAR), // destination  
            SRVNVARCHAR, lstrlenW(unicodeColumnData)*sizeof(WCHAR),  
            unicodeColumnData); //source  
        if (FAIL == retval)  
        {  
            lstrcpyW (unicodeErrorMessage, L"srv_describe failed.");  
            goto Error;  
        }  
  
       retval = srv_sendrow(srvproc);  
        if (FAIL == retval)  
        {  
            lstrcpyW (unicodeErrorMessage, L"srv_sendrow failed.");  
            goto Error;  
        }  
  
        retval = srv_senddone (srvproc, SRV_DONE_MORE|SRV_DONE_COUNT, 0, 1);  
        if (FAIL == retval)  
        {  
            lstrcpyW (unicodeErrorMessage, L"srv_senddone failed.");  
            goto Error;  
        }  
  
        return 0;  
    Error:  
        // convert error message from Unicode to multibyte.  
        retval = WideCharToMultiByte(    
            serverCodePage,                 // code page  
            0,                              // default  
            unicodeErrorMessage,            // wide-character string  
            -1,                             // string is null terminated  
            multibyteErrorMessage,          // address of buffer for new  
                                            //   string  
            sizeof (multibyteErrorMessage), // size of buffer  
            NULL, NULL);  
  
    srv_sendmsg(srvproc, SRV_MSG_ERROR, XP_ERROR_NUMBER, SRV_INFO, 1,  
                NULL, 0, __LINE__,   
                multibyteErrorMessage,  
                SRV_NULLTERM);  
  
        srv_senddone(srvproc, (SRV_DONE_ERROR | SRV_DONE_MORE), 0, 0);  
  
        return 1;  
    }  
  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="8029a-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8029a-116">See Also</span></span>  
 [<span data-ttu-id="8029a-117">srv_wsendmsg &#40;API de procedimento armazenado estendido&#41;</span><span class="sxs-lookup"><span data-stu-id="8029a-117">srv_wsendmsg &#40;Extended Stored Procedure API&#41;</span></span>](../extended-stored-procedures-reference/srv-wsendmsg-extended-stored-procedure-api.md)  
  
  
