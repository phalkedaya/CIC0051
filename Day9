#!/bin/bash -x
echo "Welcome to Employee Wage Computation Program on Master Branch";
isPresent=1;
PART_TIME=1;
FULL_TIME=2;
EMP_WAGE_PER_HR=20;
NUM_WORKING_DAYS=20;
MAX_HRS_IN_MONTH=100;
totalEmpHrs=0;
totalWorkingDays=0;
Attendance=$(( $RANDOM%2 ));
if [[ $Attendance -eq $isPresent ]]
then
	echo "The Employee is Present";
	declare -A empDailyWage;
	function getworkhrs()
	{
		local empCheck=$1;
		case $empCheck in
			$FULL_TIME) empHrs=8 ;;
			$PART_TIME) empHrs=4 ;;
			*) empHrs=0 ;;
		esac
		echo $empHrs;
	}
	while [[ $totalEmpHrs -lt $MAX_HRS_IN_MONTH && $totalWorkingDays -lt $NUM_WORKING_DAYS ]]
	do
		((totalWorkingDays++));
		empCheck=$(( $RANDOM%3 ));
		empHrs=$( getworkhrs $empCheck );
		totalEmpHrs=$(( $totalEmpHrs+$empHrs ));
		empDailyWage["Day" $totalWorkingDays]=$(( $empHrs * $EMP_WAGE_PER_HR ));
	done
	totalSalary=$(( $totalEmpHrs * $EMP_WAGE_PER_HR ));
	echo ${empDailyWage[@]};
	echo ${!empDailyWage[@]};
else
	echo "The Employee is Absent";
fi
