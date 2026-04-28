# PROG103_Assignment1_CarsonJonah_905005841
# Attendance Tracking System (ATS)
# PROG103 Assignment 1
# Student Result Management Terminal System (SRMTS)
# Author: [Carson Jonah]
# Date:  28 April 2026
# Constants
MAX_STUDENTS = 50
# Global list to store attendance records
attendance_records = []
# Function to add attendance
def add_attendance():
    name = input("Enter student name: ")
    status = input("Enter attendance status (Present/Absent): ").capitalize()
    record = {"name": name, "status": status}
    attendance_records.append(record)
    print(f"Attendance recorded for {name} as {status}.\n")


# Function to display attendance
def display_attendance():
    print("\n--- Attendance Records ---")
    for i, record in enumerate(attendance_records, start=1):
        print(f"{i}. {record['name']} - {record['status']}")
    print("--------------------------\n")

# Function to calculate summary
def attendance_summary():
    present_count = sum(1 for r in attendance_records if r["status"] == "Present")
    absent_count = sum(1 for r in attendance_records if r["status"] == "Absent")
    print("\n--- Attendance Summary ---")
    print(f"Total Students: {len(attendance_records)}")
    print(f"Present: {present_count}")
    print(f"Absent: {absent_count}")
    print("--------------------------\n")

# Main program loop
def main():
    while True:
        print("Attendance Tracking System")
        print("1. Add Attendance")
        print("2. Display Attendance")
        print("3. Attendance Summary")
        print("4. Exit")

        choice = input("Enter your choice: ")

        if choice == "1":
            add_attendance()
        elif choice == "2":
            display_attendance()
        elif choice == "3":
            attendance_summary()
        elif choice == "4":
            print("Exiting system. Goodbye!")
            break
        else:
            print("Invalid choice. Try again.\n")


# Run program
if __name__ == "__main__":
    main()
