# MY LIFE PLAN: 
heading format: 
    date: YYYY-MM-DD
    <date > - <title> 

NOTE: 
    I have to do fresher in the summer 
        -> i have 6 months left 
    After done doing fresher: 
        i have a 7th semester to keep learning ?? 

Ideal Timeline: 
    6th Semester(very busy preparing for CV, ) -> Fresher (summer)-> 7th Semester (Preparing for leaving school)
    -> 8th Semester (already out of school)
    -> Total time left: 4 + 2 + 4  = 10 months left (to be out of school)

Backup Timeline (in case i CAN'T FIND FRESHER IN SUMMER): 
    6th Semester(very busy preparing for CV) -> Can't find Fresher (summer)-> 7th Semester (Doing fresher)
    -> 8th Semester (Preparing for leaving school)
    -> Total time left: 4 + 2 + 4  = 10 months left (to be out of school)

-> TOP PRIORITY: 
    FRESHER (spend the whole 6h Semester for preparing the interview (knowledge, projects, CV) -> only 4 months left :)) ) 
    -> I may have to REMOVE SOME OF THE SUBJECTS (at school) to make things lighter for me the to prepare the CV
## -> 


## IMPORTANT TIMEPOINTS: 
        + Summer Fresher: 
            + Preparations points: <date> 
            + Endpoints: <date> 

        + 7th Semester: 
            + Preparations points: <date> 
            + Endpoints: <date> 

        + 8th Semester: 
            + Preparations points: <date>  
            + Endpoints: <date> 

## 2023-12-21 - PLAN FOR FRESHER INTERVIEW: 
    + The time i have left: 2023-12-29 -> 2024-06-1
        6 months left :))

    + things need to be done before 2024-06-1: 
        Preparing for jobs: 
            + fresher CV with 2 projects/websites with Java: 
                + ...
                + ...
                -> time estimate: 
            + gui CV xin viec (during summer): 
                + knowledges to prepare:  
                    + OOP  
                    + DSA 
                    + Networking
                    + Operating System
                    + IQ math (toan danh gia nang luc ??)
                    ... 
                -> when to start learning these things ?? 
                    ...

        Preparing for LEAVING SCHOOL: 
            + bang lai xe (bottle neck): 
                + when to start on learning: 
                    ... 
                    -> time estimate: 1 month on both theory and practice 
                + when to attent: 
                    ... 

            + bang TOEIC:  
                + when to start on learning: 
                    ... 
                    -> time estimate: 1 month
                + when to attent: 
                    + doc, viet 
                    + nghe, noi

TODO: 
    CV oriented: i might have to stop reading too many books in order to focus on finishing the things that should be done.
    After having a solid plan: 
        -> stop anything that is unrelated to the overall plan 
        -> JUST FOCUS ON FINISHING THE PLAN AS FAST AS POSSIBLE :))

## DKHP hk6: 
    NT204.O21.ATCL;
    NT204.O21.ATCL.1;

    NT230.O22.ATCL;
    NT230.O22.ATCL.1;

    NT213.O22.ATCL;
    NT213.O22.ATCL.1;

    SE334.O21.PMCL;
    SE334.O21.PMCL.1;

    SE356.O22.PMCL;
    SE356.O22.PMCL.1;


SE334.O21.PMCL.1,SE356.O22.PMCL.1,SE334.O21.PMCL,SE356.O22.PMCL,NT204.O21.ATCL,NT204.O21.ATCL.1,NT213.O22.ATCL,NT213.O22.ATCL.1,NT230.O22.ATCL,NT230.O22.ATCL.1

script: 
// Chỉ cần thay mỗi môn trên một hàng cho biến monDangKy này là xong
// Lưu ý: Nếu sau này trường update website, các thẻ query không còn đúng nữa, thì bạn liên hệ messenger.com/t/loia5tqd001 để báo mình nhé

var monDangKy = `
SE334.O21.PMCL.1
SE356.O22.PMCL.1
SE334.O21.PMCL
SE356.O22.PMCL
NT204.O21.ATCL
NT204.O21.ATCL.1
NT213.O22.ATCL
NT213.O22.ATCL.1
NT230.O22.ATCL
NT230.O22.ATCL.1
`;

var successLog = (message) => console.log('%c' + message, 'font-weight:bold; color:green;');
var errorLog = (message) => console.log('%c' + message, 'font-weight:bold; color:red;');

DangKy(monDangKy);

function DangKy(monDangKyString) {
  try {
    var listMonDangKy = monDangKyString.trim().split('\n').map((it) => it.trim())
    
    var allRows = [...document.querySelectorAll('form table tr')]

    var rowsToDangKy = allRows.filter((it) => listMonDangKy.includes(it.querySelector('td:nth-child(2)')?.textContent?.trim()))
    
    rowsToDangKy.forEach((it, index) => {
      it.querySelector('td:first-child input[type="checkbox"]').click();
      var tenLop = it.querySelector('td:nth-child(2)')?.textContent?.trim();
      successLog(index + 1 + '.Đã chọn lớp ' + tenLop);
    })
  } catch {
    errorLog('Chọn lớp không thành công! Bạn tự chọn lớp đi nhé!');
  }
}
