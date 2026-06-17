# project-1
# Smart Online Election System

candidates = {
    "1": "Candidate A",
    "2": "Candidate B",
    "3": "Candidate C"
}

votes = {
    "Candidate A": 0,
    "Candidate B": 0,
    "Candidate C": 0
}

voted_voters = []

while True:
    print("\n===== SMART ONLINE ELECTION =====")
    print("1. Cast Vote")
    print("2. View Results")
    print("3. Exit")

    choice = input("Enter your choice: ")

    if choice == "1":
        voter_id = input("Enter Voter ID: ")

        if voter_id in voted_voters:
            print("You have already voted!")
            continue

        print("\nCandidates:")
        for key, value in candidates.items():
            print(f"{key}. {value}")

        vote = input("Select candidate number: ")

        if vote in candidates:
            selected_candidate = candidates[vote]
            votes[selected_candidate] += 1
            voted_voters.append(voter_id)

            print(f"Vote successfully cast for {selected_candidate}")
        else:
            print("Invalid candidate selection!")

    elif choice == "2":
        print("\n===== ELECTION RESULTS =====")
        for candidate, count in votes.items():
            print(f"{candidate}: {count} votes")

    elif choice == "3":
        print("Election System Closed")
        break

    else:
        print("Invalid choice!")








